# Architecture

> "The architecture is basically: one file with math in it and a window on top."

That's mostly accurate, but let's be more precise.

---

## File Layout

```
pyLoan/
└── pyLoan.py        ← Everything lives here. Yes, everything.
```

This is an intentional single-file design. No packages, no modules, no `__init__.py` hierarchies. It's approachable, portable, and makes the architecture diagram refreshingly short.

---

## Logical Layers

Despite being one file, pyLoan has clear separation of concerns between three layers:

### Layer 1 — Calculation Layer (Pure Functions)

Module-level functions that contain zero UI state. They take numbers in, return numbers out. Side-effect free. Could be tested in isolation without instantiating any Qt objects.

```python
calculate_emi(principal, annual_rate, tenure_years)
    └── Standard amortisation formula
    └── Special case: monthly_rate == 0 → P / n

calculate_outstanding_principal(principal, annual_rate, tenure_years, paid_months)
    └── Remaining principal balance after N payments
    └── Special case: monthly_rate == 0 → linear interpolation

calculate_new_emi_after_lump(principal, annual_rate, tenure_years, lump_sum, nth_year)
    └── Calls calculate_outstanding_principal for balance at nth_year
    └── Calls calculate_emi with new_principal and remaining tenure
```

**Why pure functions?** Because testability. Because clarity. Because it means the GUI is never doing math, and the math is never doing GUI.

---

### Layer 2 — GUI Layer (EMICalculator class)

`EMICalculator(QWidget)` owns the entire user interface. It:

- Sets up the dark theme via `QPalette` and a Qt stylesheet
- Builds the widget tree inside `init_ui()`:
  - `QTabWidget` with two tabs: Calculator and Graphs
  - `QGroupBox` containers for logical input groups
  - `QLineEdit` fields with `QDoubleValidator`/`QIntValidator`
  - `QLabel` for results (HTML-formatted)
  - `FigureCanvasQTAgg` embedding matplotlib in the Qt widget tree
- Handles the Calculate button click in `on_calculate()`:
  - Parses inputs
  - Validates boundaries
  - Calls the calculation layer
  - Formats and displays results
  - Calls `plot_graphs()`
- Renders three charts in `plot_graphs()`:
  - Payment breakdown pie
  - Outstanding principal decay line chart
  - EMI component stacked area chart

---

### Layer 3 — Entry Point

```python
if __name__ == "__main__":
    app = QApplication(sys.argv)
    win = EMICalculator()
    win.show()
    sys.exit(app.exec_())
```

Standard Qt boilerplate. `QApplication` owns the event loop. `EMICalculator.show()` makes the window visible. `exec_()` blocks until the window closes.

---

## Data Flow Summary

```
User Input (QLineEdit)
    ↓
on_calculate() — validates + parses
    ↓                          ↓
Calculation Layer          plot_graphs()
    ↓                          ↓
lbl_result (HTML text)     FigureCanvas.draw()
```

---

## Design Decisions

| Decision | Rationale |
|---|---|
| Single file | Maximum approachability; no install-time confusion |
| Pure functions for math | Testable without Qt; clear separation |
| PyQt5 for GUI | Mature, cross-platform, great Qt widget library |
| Matplotlib via FigureCanvasQTAgg | Embedded charts without a browser or web view |
| Dark theme via QPalette + stylesheet | Full system-level + widget-level theming |
| `int(tenure * 12)` before `np.arange` | Prevents float-stepping artifacts in chart x-axis |

---

## Chart Architecture

The Graphs tab holds a single `matplotlib.figure.Figure` embedded via `FigureCanvasQTAgg`. On each calculation, `plot_graphs()` calls `figure.clear()` and redraws from scratch using a `2×2` `GridSpec` layout:

```
┌────────────────┬────────────────┐
│ gs[0, 0]       │ gs[0, 1]       │
│ Pie Chart      │ Line Chart     │
│ (breakdown)    │ (outstanding)  │
├────────────────┴────────────────┤
│ gs[1, :]                        │
│ Stacked Area (EMI components)   │
└─────────────────────────────────┘
```

All chart axes use explicit dark background colours (`#2A2A2A`) and white tick labels to match the application theme.

---

*[← Back to Home](Home.md)*
