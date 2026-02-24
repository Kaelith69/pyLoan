# Troubleshooting

Something went wrong. It's okay. Let's fix it.

---

## The Window Doesn't Open / App Crashes Immediately

### Check your Python version

```bash
python --version
```

Needs to be 3.8 or newer. If it says Python 2.x, you're living in the past.

### Check your dependencies

```bash
pip show PyQt5 matplotlib numpy
```

If any of those say `not found`, install them:

```bash
pip install PyQt5 matplotlib numpy
```

### On Linux: Missing Qt platform plugin

**Error looks like:**
```
qt.qpa.plugin: Could not load the Qt platform plugin "xcb" in "" even though it was found.
```

**Fix:**
```bash
sudo apt-get install libxcb-icccm4 libxcb-image0 libxcb-keysyms1 libxcb-randr0 \
    libxcb-render-util0 libxcb-xinerama0 libxcb-xfixes0
```

Or try setting the platform manually:
```bash
QT_QPA_PLATFORM=xcb python pyLoan.py
```

### On Linux: Running in a headless environment

PyQt5 requires a display. If you're on a server with no GUI:
```
_tkinter.TclError: no display name and no $DISPLAY environment variable
```

pyLoan is a desktop app. It needs a screen. Use it on a desktop machine.

---

## "Please enter valid numeric values" Error

You've got something non-numeric in one of the input fields. Check for:

- Commas instead of decimal points (use `.` not `,` for decimals in the fields)
- Spaces or letters accidentally typed
- Empty fields (all four Loan Parameters fields are required)

---

## Results Look Wrong / EMI Seems Too High

The most common cause: **interest rate was entered as a decimal instead of a percentage**.

The field expects `8.5` for 8.5% annual interest — **not** `0.085`. If you entered `0.085`, the app is treating that as 0.085% which is basically free money, so the EMI would be surprisingly low. Enter `8.5`.

---

## The Graphs Tab Shows Nothing

Charts only render after you click **Calculate EMI**. If you switch to the Graphs tab before calculating, you'll see a blank dark canvas. That's expected. Calculate first, then switch tabs.

---

## Graphs Look Distorted or Clipped

Try resizing the window. The matplotlib canvas scales with the window. Making the window taller/wider usually helps charts breathe.

---

## Lump-Sum Results Don't Appear

The lump-sum section only produces output if:

1. **Lump sum is > 0** — leaving it blank or entering 0 skips prepayment simulation
2. **Year N is between 1 and (tenure - 1)** — you can't prepay before year 1 or after the loan is done

If year N ≥ tenure, no prepayment output is shown.

---

## The App is Slow / Charts Take Long to Render

This is most likely matplotlib rendering time on a slow machine. The chart generation iterates over every month in the loan (up to `tenure × 12` iterations), so a 30-year loan with monthly data points means ~360 calculations per chart.

On a modern machine this should still be under a second. If it's taking longer, check if your system is under heavy load.

---

## `ModuleNotFoundError: No module named 'PyQt5'`

You're either:

1. Not in the virtual environment — activate it: `source .venv/bin/activate`
2. Running a different Python than the one where you installed packages — check `which python` vs `which pip`

---

## `ImportError: DLL load failed` (Windows)

You may have a version mismatch between PyQt5 and its Qt5 DLLs. Try:

```bash
pip uninstall PyQt5 PyQt5-Qt5 PyQt5-sip
pip install PyQt5
```

---

## The `₹` Symbol Shows as `?` or a Box

Your terminal or font doesn't support the Rupee sign. This doesn't affect app functionality — it's a display issue in your terminal output only. The app window itself uses Qt's rendering which handles Unicode correctly.

---

## Still Stuck?

[Open an issue](https://github.com/Kaelith69/pyLoan/issues) on GitHub. Include:

- Your OS and version
- Your Python version (`python --version`)
- Your PyQt5 version (`pip show PyQt5`)
- The full error message / stack trace
- What you were trying to do

We'll take a look. We're not fast, but we're thorough. 🔍

---

*[← Usage](Usage.md) · [Back to Home](Home.md)*
