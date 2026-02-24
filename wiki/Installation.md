# Installation

Getting pyLoan running is not complicated. If you've installed a Python package before, you've got this. If you haven't — this is a great time to start.

---

## Prerequisites

| Requirement | Version | Notes |
|---|---|---|
| Python | 3.8+ | Anything older is living dangerously |
| pip | Latest | Comes with Python |
| OS | Windows / macOS / Linux | All three work |

That's it. No Docker. No Node.js. No cloud account. No credit card.

---

## Step 1 — Clone the Repository

```bash
git clone https://github.com/Kaelith69/pyLoan.git
cd pyLoan
```

If you don't have git, you can also download the ZIP from the GitHub page and unzip it.

---

## Step 2 — Create a Virtual Environment (Recommended)

You don't *have* to use a virtual environment, but future-you will appreciate the isolation.

```bash
# Create the venv
python -m venv .venv

# Activate it
source .venv/bin/activate      # macOS / Linux
.venv\Scripts\activate         # Windows (Command Prompt)
.venv\Scripts\Activate.ps1     # Windows (PowerShell)
```

Your terminal prompt should now have `(.venv)` at the front. That's the sign it worked.

---

## Step 3 — Install Dependencies

```bash
pip install PyQt5 matplotlib numpy
```

Three packages. That's the entire dependency list. You're welcome.

| Package | Why It's Needed |
|---|---|
| `PyQt5` | The GUI framework — windows, buttons, inputs |
| `matplotlib` | Chart rendering |
| `numpy` | Array operations for chart data generation |

---

## Step 4 — Run It

```bash
python pyLoan.py
```

A dark-themed window should open. If it does, you're done. 🎉

---

## Platform-Specific Notes

### Linux

Some distributions don't ship Qt5 system libraries by default. If you get errors about missing Qt platforms:

```bash
sudo apt-get install python3-pyqt5
# or
sudo dnf install python3-qt5
```

If you see `Could not load the Qt platform plugin "xcb"`:

```bash
sudo apt-get install libxcb-icccm4 libxcb-image0 libxcb-keysyms1 libxcb-randr0 \
    libxcb-render-util0 libxcb-xinerama0 libxcb-xfixes0
```

### macOS

If pip-installed PyQt5 doesn't find system Qt libraries, try:

```bash
pip install pyqt5-qt5 pyqt5
```

### Windows

Should generally work out of the box. If you get a DLL error, make sure you're running the Python from your venv and not a system Python.

---

## Verifying Your Install

Once the window opens:

1. Type `1000000` in the Total Loan field
2. Type `8.5` in the Interest Rate field
3. Type `10` in the Tenure field
4. Click **Calculate EMI**

You should see results appear in the bottom panel. Switch to the **Graphs** tab to see three charts. If all that works, installation is complete.

---

## Uninstalling

```bash
# Deactivate venv if active
deactivate

# Delete the project folder
rm -rf pyLoan/    # macOS/Linux
rd /s /q pyLoan   # Windows
```

No registry entries. No system files. It's just a folder with Python files. Delete it and it's gone.

---

*[← Back to Home](Home.md) · [Usage →](Usage.md)*
