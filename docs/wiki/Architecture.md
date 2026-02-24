# Architecture

This page explains how pyLoan is structured — both the high-level design and the reasoning behind it. If you want to contribute, this is the first page to read.

---

## Overview

pyLoan is intentionally a **single-file application**. All code lives in `pyLoan.py`. This is a deliberate design choice to keep the project approachable: one file to clone, one file to read, one file to debug. There's no package hierarchy, no `__init__.py` mystery tour, no "where is the entry point again?" moment.

The code is divided into two conceptual layers:

```
pyLoan.py
│
├── Calculation Engine (module-level functions)
│   ├── calculate_emi()
│   ├── calculate_outstanding_principal()
│   └── calculate_new_emi_after_lump()
│
└── GUI Layer (EMICalculator class)
    ├── setup_dark_theme()
    ├── init_ui()
    ├── on_calculate()
    └── plot_graphs()
```

---

## Calculation Engine

The three `calculate_*` functions are **pure Python**. They accept only numeric arguments and return a float. They have no knowledge of Qt, matplotlib, or any UI concept.

This separation is important because:

1. **Testability** — you can call these functions directly in a test without instantiating a Qt application.
2. **Reusability** — if someone wants to import just the math (e.g., write a CLI wrapper), they can.
3. **Clarity** — the business logic is not tangled up with widget state.

### `calculate_emi(principal, annual_rate, tenure_years)`

Implements the standard amortisation formula:

```
        P · r · (1 + r)^n
EMI = ─────────────────────
          (1 + r)^n − 1
```

Where `r = annual_rate / 100 / 12` (monthly rate) and `n = int(tenure_years * 12)` (total months).

Edge case handled: when `annual_rate == 0`, the formula produces `0/0`. The function returns `principal / total_months` instead.

### `calculate_outstanding_principal(principal, annual_rate, tenure_years, paid_months)`

Returns the remaining loan balance after `paid_months` payments, using:

```
outstanding = P * ((1+r)^n - (1+r)^m) / ((1+r)^n - 1)
```

Where `m` is `paid_months`. Edge case: when `r == 0`, uses linear interpolation: `P * (n - m) / n`.

### `calculate_new_emi_after_lump(principal, annual_rate, tenure_years, lump_sum, nth_year)`

1. Computes the outstanding balance at `nth_year * 12` months.
2. Subtracts `lump_sum` from the outstanding balance (`max(0, outstanding - lump_sum)`).
3. Calls `calculate_emi` with the reduced principal and remaining tenure.

Returns `0.0` if the lump sum fully covers the outstanding balance.

---

## GUI Layer

The `EMICalculator(QWidget)` class owns everything UI-related.

### `setup_dark_theme()`

Configures a `QPalette` with dark background/foreground colours and applies it to the widget. This runs before `init_ui` so that child widgets inherit the palette from the start.

### `init_ui()`

Builds the entire widget tree:

- `QTabWidget` with two tabs: **Calculator** and **Graphs**
- Calculator tab: `QGroupBox` for loan parameters, `QGroupBox` for lump-sum prepayment, a calculate button, and a `QFrame` results panel
- Graphs tab: a `FigureCanvasQTAgg` wrapping a matplotlib `Figure`
- All input fields use `QDoubleValidator` or `QIntValidator` to reject non-numeric keystrokes before they reach `on_calculate`

### `on_calculate()`

1. Reads and parses all input fields (raises a `QMessageBox` warning on `ValueError`).
2. Computes `principal = loan - down`.
3. Validates that `principal > 0`, `rate >= 0`, and `tenure > 0`.
4. Calls `calculate_emi`, formats results as HTML, and sets them on the `QLabel`.
5. Calls `plot_graphs` to refresh the charts.

### `plot_graphs()`

Uses a `2×2` matplotlib `GridSpec`:

| Position | Chart | Type |
|---|---|---|
| `[0, 0]` | Payment Breakdown | Pie |
| `[0, 1]` | Outstanding Principal Over Time | Line |
| `[1, :]` | EMI Components Over Time | Stacked Area |

The figure background is set to match the dark Qt theme (`#2A2A2A`). `canvas.draw()` is called after all axes are populated.

---

## Dependencies

| Library | Role |
|---|---|
| `PyQt5` | Widgets, layouts, validators, theming |
| `matplotlib` | Chart rendering via `FigureCanvasQTAgg` |
| `numpy` | Month array generation (`np.arange`) for chart X-axes |
| `sys` | `QApplication` argv passing and `sys.exit` |

No other dependencies. No internet. No magic.

---

## Entry Point

```python
if __name__ == "__main__":
    app = QApplication(sys.argv)
    win = EMICalculator()
    win.show()
    sys.exit(app.exec_())
```

Standard Qt pattern. `exec_()` starts the event loop. `sys.exit` ensures the process exits cleanly with the Qt application's return code.
