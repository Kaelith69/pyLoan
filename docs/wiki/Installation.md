# Installation

Everything you need to get pyLoan running. It's shorter than you think.

---

## Prerequisites

| Requirement | Minimum Version | Notes |
|---|---|---|
| Python | 3.8 | Earlier versions are untested and probably unhappy |
| pip | Any recent | Comes with Python — you're probably fine |
| Qt5 libraries | System-level (Linux only) | See Linux section below |

---

## Step 1 — Clone the Repository

```bash
git clone https://github.com/Kaelith69/pyLoan.git
cd pyLoan
```

---

## Step 2 — Create a Virtual Environment (Recommended)

You don't *have* to use a virtual environment, but you should. Mixing global pip packages is how computers become sad.

```bash
# Create the environment
python -m venv .venv

# Activate it
source .venv/bin/activate      # macOS / Linux
.venv\Scripts\activate         # Windows (Command Prompt)
.venv\Scripts\Activate.ps1     # Windows (PowerShell)
```

---

## Step 3 — Install Dependencies

```bash
pip install PyQt5 matplotlib numpy
```

That's three packages. No `requirements.txt` labyrinth, no 200-dependency tree, no Rust compilation step. Just three packages.

---

## Step 4 — Run

```bash
python pyLoan.py
```

The dark-themed window appears. If it doesn't, see [Troubleshooting](Troubleshooting.md).

---

## Platform-Specific Notes

### macOS

If you hit an SSL error (`[SSL: CERTIFICATE_VERIFY_FAILED]`) during pip install:

```bash
pip install --upgrade certifi
```

On Apple Silicon, PyQt5 via pip should work fine with Python 3.9+. If you hit binary compatibility issues, consider using `brew install pyqt5` instead.

### Linux

Some distributions package Qt5 separately from the Python bindings. If pyLoan fails to launch with a Qt platform plugin error, install the system packages:

**Debian / Ubuntu:**
```bash
sudo apt-get install python3-pyqt5 python3-pyqt5.qtwidgets
```

**Fedora / RHEL:**
```bash
sudo dnf install python3-qt5
```

**Arch:**
```bash
sudo pacman -S python-pyqt5
```

If you're on a headless server (no display), pyLoan won't run — it requires a desktop environment. That is by design.

### Windows

Standard pip install should work out of the box. If you hit a `DLL load failed` error, ensure you're using a 64-bit Python interpreter and that your Visual C++ redistributable is up to date.

---

## Verifying the Installation

```bash
python -c "import PyQt5; import matplotlib; import numpy; print('All good.')"
```

If that prints `All good.`, you're ready. If it prints a stack trace, something went wrong — head to [Troubleshooting](Troubleshooting.md).

---

## No Internet Required

Once installed, pyLoan runs entirely offline. There are no update checks, no license validation calls, no telemetry pings. Your pip cache is the only external dependency after installation.
