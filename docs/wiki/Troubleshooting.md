# Troubleshooting

Things that might go wrong and how to fix them. We've tried to anticipate your misery.

---

## The Window Doesn't Open

### Symptom
Running `python pyLoan.py` returns immediately with no window, or throws an error immediately.

### Common Causes & Fixes

**`ModuleNotFoundError: No module named 'PyQt5'`**

You haven't installed the dependencies yet.
```bash
pip install PyQt5 matplotlib numpy
```

**`ModuleNotFoundError: No module named 'matplotlib'` or `'numpy'`**

Same fix. All three must be installed.

**`qt.qpa.xcb: could not connect to display` (Linux)**

You're running in a headless environment (no desktop). pyLoan requires a display. Use a machine with a desktop environment or set up X forwarding.

**`ImportError: DLL load failed` (Windows)**

You're likely using a 32-bit Python on a 64-bit system, or your Visual C++ Redistributable is outdated. Install the 64-bit Python from [python.org](https://python.org) and retry.

---

## The Charts Don't Update

### Symptom
You click **Calculate EMI** and the results appear in the text area, but the **Graphs** tab shows nothing or shows old data.

### Fix

Switch to the **Graphs** tab *after* clicking **Calculate EMI**. The charts render on calculate, not on tab switch. They should be visible as soon as you switch over.

If charts still appear blank after switching tabs, try resizing the window slightly — this forces a Qt repaint event. If they remain blank, check the terminal output for matplotlib warnings.

---

## Calculation Results Seem Wrong

### Symptom
The EMI or total payment shown doesn't match what your bank quoted.

### Explanation

pyLoan uses the **standard reducing-balance amortisation formula**. This is the most common formula used by banks globally. However:

- Some banks use a **flat-rate** calculation (where interest is computed on the original principal throughout). pyLoan does not support flat-rate loans.
- Some banks calculate EMI with **daily compounding** rather than monthly. pyLoan uses monthly compounding.
- **Processing fees, insurance premiums, and GST** are not factored in. pyLoan shows the pure EMI, not the total cost of the loan.

If your bank uses a different formula, the results will differ. When in doubt, verify with your bank's own calculator.

---

## Input Field Rejects My Value

### Symptom
You try to type a decimal number and the field refuses some keystrokes.

### Explanation

Fields use `QDoubleValidator` with defined ranges:

| Field | Allowed range |
|---|---|
| Downpayment | 0 – 1,000,000,000 |
| Total Loan | 0 – 1,000,000,000 |
| Interest Rate | 0 – 100 |
| Tenure | 0 – 100 years |
| Lump Sum | 0 – 1,000,000,000 |
| At Year | 0 – 100 (integer) |

If your value exceeds these ranges, the field will reject the keystrokes. For the vast majority of real-world loans, these bounds are more than sufficient. If you genuinely need a ₹1B+ loan calculator, we're impressed and slightly worried.

**Locale note:** Depending on your system locale, the decimal separator might be `,` (comma) instead of `.` (dot). If decimal input is being rejected, try the other separator.

---

## The App Crashes on Launch (macOS)

### Symptom
On macOS, the app crashes immediately or shows a permission dialog.

### Fix

macOS may block PyQt5 apps from the first launch. Try right-clicking `Terminal.app` → **Open** → run `python pyLoan.py` from there. If you installed Python via Homebrew, ensure you're using the Homebrew Python, not the system Python.

---

## `ZeroDivisionError` in the Terminal

### Symptom
A `ZeroDivisionError` appears in the terminal output.

### This Should Not Happen in v1.1.0

Both `calculate_emi` and `calculate_outstanding_principal` have explicit `monthly_rate == 0` guards since v1.1.0. If you're seeing this, you may be on v1.0.0. Check your version first:

```bash
git log --oneline -1
```

If it shows the initial commit rather than the v1.1.0 refactor commit, pull the latest changes:

```bash
git pull origin main
```

> **Note:** If you have local uncommitted changes, stash them first with `git stash` to avoid merge conflicts.

If you're already on v1.1.0 and still seeing this, please [open an issue](https://github.com/Kaelith69/pyLoan/issues) with the full stack trace.

---

## Something Else Is Broken

Check the [GitHub Issues](https://github.com/Kaelith69/pyLoan/issues) to see if it's already reported. If not, open a new issue with:

1. Your OS and version
2. Your Python version (`python --version`)
3. Your PyQt5 version (`python -c "import PyQt5; print(PyQt5.QtCore.PYQT_VERSION_STR)"`)
4. The full error message and stack trace from the terminal

We'll take a look.
