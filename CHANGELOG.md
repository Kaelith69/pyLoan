# Changelog

All notable changes to **pyLoan** are documented here.

Format loosely follows [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), versioned with [Semantic Versioning](https://semver.org/). The format is: if it broke you and we fixed it, it's in here.

---

## [1.1.0] — 2024 — Refactor & Bug-Fix Release

### Fixed

- **Division by zero at 0% interest rate** — `calculate_emi` would attempt `P * 0 * 1 / (1 - 1)` and throw a `ZeroDivisionError`. Added `if monthly_rate == 0: return principal / total_months` branch. Your interest-free loan from a generous relative is now supported.

- **Division by zero at 0% interest rate (outstanding principal)** — Same root cause in `calculate_outstanding_principal`. Added a linear-interpolation branch: `max(0.0, principal * (total_months - paid_months) / total_months)`. Fixed the bug where reality stopped working at `r=0`.

- **Fractional month indices in matplotlib plots** — When `tenure` was a non-integer (e.g. `1.5` years), `np.arange(1, tenure * 12 + 1)` produced floating-point steps, causing misaligned chart data. Now uses `total_months = int(tenure * 12)` before generating the range. Charts are now honest about what month it is.

- **No guard for `tenure ≤ 0`** — Passing zero or negative tenure produced `total_months = 0`, causing a downstream divide-by-zero. Added an explicit check in `on_calculate` with a clear user-facing warning dialog. The calculator now refuses to compute a loan that doesn't exist in time.

- **No guard for `rate < 0`** — Negative interest rates produce mathematically undefined / economically absurd results. Added to the same runtime validation block. If your bank is paying *you* interest at a negative rate, congratulations, but pyLoan can't help you there.

### Changed

- `plot_graphs` now uses `int(tenure * 12)` throughout instead of relying on implicit float-to-int coercion.
- `calculate_outstanding_principal` now explicitly returns `0.0` (not a small float near zero) when the loan is fully paid.
- Improved QSS stylesheet with `border-radius`, `padding`, and focus states for a more polished dark UI.
- `QGroupBox` titles now use the header font consistently.

### Added

- `QFrame` results panel with a visible border to visually separate inputs from outputs.
- `QScrollArea` import (reserved for future use in an expanded results view).

---

## [1.0.0] — Initial Release

### Added

- EMI calculator using the standard amortisation formula.
- Lump-sum prepayment simulation with revised EMI and total savings calculation.
- Dark theme via `QPalette` and a full `QStyleSheet`.
- Three matplotlib charts embedded via `FigureCanvasQTAgg`:
  - Payment Breakdown (Pie)
  - Outstanding Principal Over Time (Line)
  - EMI Components Over Time (Stacked Area)
- `QDoubleValidator` and `QIntValidator` on all input fields.
- Tabbed layout separating the calculator inputs from the graphs.

---

*If a version isn't listed here, it either didn't happen or it was embarrassing enough that we chose to forget.*
