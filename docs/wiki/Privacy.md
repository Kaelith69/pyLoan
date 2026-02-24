# Privacy

Short version: **pyLoan collects nothing, stores nothing, and sends nothing anywhere.**

Longer version: keep reading.

---

## What Data pyLoan Processes

When you use pyLoan, you enter:

- A downpayment amount
- A total loan amount
- An interest rate
- A loan tenure
- (Optionally) a lump sum and year

These values are held **in memory only** — specifically in the `text()` values of `QLineEdit` widgets. They are read by `on_calculate()`, used to compute results, and displayed on screen. That is the entire lifecycle of your data.

---

## What pyLoan Does NOT Do

| Action | Does pyLoan do this? |
|---|---|
| Connect to the internet | ❌ Never |
| Send data to a server | ❌ Never |
| Write data to disk | ❌ Never |
| Read environment variables or system info | ❌ Never |
| Load external plugins or scripts | ❌ Never |
| Log keystrokes or field values | ❌ Never |
| Use analytics or telemetry SDKs | ❌ Never |
| Phone home for updates | ❌ Never |
| Require an account or sign-in | ❌ Never |

---

## Data Lifetime

Your input data exists only while the application window is open.

- The moment you close the window, the `EMICalculator` widget is destroyed and all field values are garbage-collected.
- There is no session state, no auto-save, and no recovery mechanism.
- There are no configuration files written to your home directory or `%APPDATA%`.

---

## Dependencies and Their Privacy Posture

pyLoan uses three third-party libraries:

| Library | Network activity | Notes |
|---|---|---|
| **PyQt5** | None at runtime | Qt5 bindings — purely local GUI |
| **Matplotlib** | None at runtime | Rendering library — no telemetry |
| **NumPy** | None at runtime | Math library — no telemetry |

None of these libraries make network calls during normal operation. If you're concerned about pip installation telemetry, that is a pip / PyPI concern, not a pyLoan concern.

---

## Source Code Auditability

pyLoan is a single file: `pyLoan.py`. You can read the entire application in one sitting (it's under 400 lines). There are no obfuscated sections, no compiled extensions, and no dynamic code loading. What you read is what runs.

---

## Summary

Your loan data is yours. pyLoan is a calculator, not a service. It has no business model, no data pipeline, and no reason to collect anything. If you don't trust that, read the source — it's 389 lines and there is nowhere to hide a network call.
