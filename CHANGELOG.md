# Changelog

All notable changes to pyLoan will be documented here.

Format follows [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),  
versioning follows [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [Unreleased]

> Things cooking in the background. No ETA. No promises. No product manager.

---

## [1.1.0] — 2026-02-24

### The "Wait, That's Actually a Bug" Release 🐛

You know that feeling when you test edge cases and your own code throws a `ZeroDivisionError` at you? Yeah. This release is that, but fixed.

### Fixed

- **ZeroDivisionError at 0% interest rate** — `calculate_emi()` was doing `P * 0 * 1 / (1 - 1)` which is famously not a number. Added `if monthly_rate == 0: return principal / total_months` branch. Interest-free loans are rare but they exist, and now we handle them.

- **ZeroDivisionError at 0% interest rate (again)** — Same problem in `calculate_outstanding_principal()`. Added matching zero-rate branch that does linear interpolation instead. Consistency: achieved.

- **Fractional month indices in plot** — `np.arange(1, tenure * 12 + 1)` was generating floats when `tenure` was a decimal (e.g. `10.5` years → `np.arange(1, 127.0)`). Changed to `total_months = int(tenure * 12)` before the range. The charts now have integer x-axis ticks like a civilised tool.

- **No guard for `tenure ≤ 0`** — Entering `0` years would cascade into `total_months = 0` and then a divide-by-zero somewhere down the call stack. Added explicit validation in `on_calculate()` with a user-facing warning dialog.

- **No guard for `rate < 0`** — Negative interest rates produce undefined (and entertaining but wrong) results. Added to the same validation block.

### Changed

- Refactored the UI layout for slightly better spacing — `setMinimumSize(900, 700)` for a roomier experience.
- Applied consistent dark theme stylesheet across all widget types.
- Graph layout uses `gridspec` with explicit `hspace`/`wspace` for tighter control.

---

## [1.0.0] — 2026-02-21

### The "It Works On My Machine" Initial Release 🎉

The beginning. A single Python file. A dream. A dark theme.

### Added

- `calculate_emi(principal, annual_rate, tenure_years)` — standard amortisation formula
- `calculate_outstanding_principal(...)` — remaining balance after N payments
- `calculate_new_emi_after_lump(...)` — revised EMI after a one-time prepayment
- `EMICalculator(QWidget)` — PyQt5 GUI with:
  - Dark theme via `QPalette` + stylesheet
  - Two-tab layout: Calculator and Graphs
  - Loan parameter input fields with validators
  - Optional lump-sum prepayment section
  - Results display panel (HTML-formatted)
  - Three matplotlib charts: pie breakdown, outstanding principal curve, EMI component stack
- `QApplication` entry point with `exec_()` event loop

---

[Unreleased]: https://github.com/Kaelith69/pyLoan/compare/v1.1.0...HEAD
[1.1.0]: https://github.com/Kaelith69/pyLoan/compare/v1.0.0...v1.1.0
[1.0.0]: https://github.com/Kaelith69/pyLoan/releases/tag/v1.0.0
