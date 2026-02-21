<div align="center">

<!-- ============================================================
     HERO SVG BANNER
     Copy everything between the svg tags and render it directly
     ============================================================ -->
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 860 200" width="860" height="200">
  <defs>
    <linearGradient id="bg" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" style="stop-color:#1a1a2e;stop-opacity:1"/>
      <stop offset="100%" style="stop-color:#16213e;stop-opacity:1"/>
    </linearGradient>
    <linearGradient id="accent" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" style="stop-color:#007ACC;stop-opacity:1"/>
      <stop offset="100%" style="stop-color:#00CC89;stop-opacity:1"/>
    </linearGradient>
    <filter id="glow">
      <feGaussianBlur stdDeviation="3" result="coloredBlur"/>
      <feMerge><feMergeNode in="coloredBlur"/><feMergeNode in="SourceGraphic"/></feMerge>
    </filter>
  </defs>
  <!-- Background -->
  <rect width="860" height="200" fill="url(#bg)" rx="12"/>
  <!-- Decorative coin circles -->
  <circle cx="760" cy="50"  r="38" fill="none" stroke="#007ACC" stroke-width="2" opacity="0.4"/>
  <circle cx="760" cy="50"  r="26" fill="none" stroke="#00CC89" stroke-width="1.5" opacity="0.3"/>
  <circle cx="800" cy="140" r="28" fill="none" stroke="#007ACC" stroke-width="2" opacity="0.25"/>
  <circle cx="60"  cy="150" r="20" fill="none" stroke="#00CC89" stroke-width="1.5" opacity="0.3"/>
  <!-- ₹ coin symbol -->
  <text x="755" y="57" font-family="Arial" font-size="26" fill="#007ACC" opacity="0.7" text-anchor="middle" filter="url(#glow)">₹</text>
  <!-- Accent bar -->
  <rect x="60" y="155" width="420" height="4" rx="2" fill="url(#accent)" opacity="0.9"/>
  <!-- Main title -->
  <text x="60" y="95" font-family="'Segoe UI', Arial, sans-serif" font-size="52" font-weight="700"
        fill="#FFFFFF" filter="url(#glow)">py</text>
  <text x="133" y="95" font-family="'Segoe UI', Arial, sans-serif" font-size="52" font-weight="700"
        fill="url(#accent)" filter="url(#glow)">Loan</text>
  <!-- Subtitle -->
  <text x="62" y="130" font-family="'Segoe UI', Arial, sans-serif" font-size="18" fill="#A0A0C0">
    Smart EMI Calculator · Dark UI · Interactive Graphs
  </text>
  <!-- Version chip -->
  <rect x="62" y="165" width="64" height="20" rx="10" fill="#007ACC" opacity="0.85"/>
  <text x="94" y="179" font-family="Arial" font-size="11" fill="#FFFFFF" text-anchor="middle">v1.1.0</text>
</svg>

---

[![Python](https://img.shields.io/badge/Python-3.8%2B-3776AB?style=flat-square&logo=python&logoColor=white)](https://www.python.org/)
[![PyQt5](https://img.shields.io/badge/PyQt5-5.x-41CD52?style=flat-square&logo=qt&logoColor=white)](https://riverbankcomputing.com/software/pyqt/)
[![Matplotlib](https://img.shields.io/badge/Matplotlib-3.x-11557C?style=flat-square&logo=matplotlib&logoColor=white)](https://matplotlib.org/)
[![NumPy](https://img.shields.io/badge/NumPy-1.x-013243?style=flat-square&logo=numpy&logoColor=white)](https://numpy.org/)
[![License](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)](LICENSE)
[![Version](https://img.shields.io/badge/version-1.1.0-blue?style=flat-square)](#-bug-fixes--changelog)
[![Code style](https://img.shields.io/badge/code%20style-PEP8-brightgreen?style=flat-square)]()

</div>

---

## 📖 Table of Contents

1. [Overview](#-overview)
2. [Features](#-features)
3. [Architecture](#-architecture)
4. [File Structure](#-file-structure)
5. [Installation](#-installation)
6. [Usage](#-usage)
7. [Core API Reference](#-core-api-reference)
8. [Visualizations](#-visualizations)
9. [Bug Fixes & Changelog](#-bug-fixes--changelog)

---

## 🔍 Overview

**pyLoan** is a desktop Loan EMI (Equated Monthly Installment) calculator built with **Python**, **PyQt5**, and **Matplotlib**. It provides a polished dark-themed GUI where users can enter loan parameters, optionally simulate a lump-sum prepayment, and instantly see:

- Their monthly instalment amount
- Total interest payable over the loan term
- Interest-to-principal breakdown
- How a mid-term lump-sum payment reduces future EMIs and total interest

All results are complemented by three interactive matplotlib charts embedded directly in the application window.

---

## ✨ Features

| Feature | Details |
|---|---|
| 🌑 **Dark Theme** | Full QPalette + stylesheet dark mode — easy on the eyes |
| 🧮 **EMI Calculation** | Standard amortisation formula with correct 0%-rate handling |
| 💰 **Lump-Sum Prepayment** | Simulates mid-term paydown and shows revised EMI + savings |
| 📊 **3 Interactive Charts** | Pie breakdown · outstanding-principal curve · stacked EMI components |
| ✅ **Input Validation** | QDoubleValidator / QIntValidator plus runtime boundary checks |
| 🛡️ **Edge-Case Safe** | Handles 0% interest rate and zero-tenure inputs without crashing |

---

## 🏗️ Architecture

```
┌───────────────────────────────────────────────────────────┐
│                     pyLoan.py                             │
│                                                           │
│  ┌─────────────────────────────────────────────────────┐  │
│  │  Pure Calculation Layer  (module-level functions)   │  │
│  │                                                     │  │
│  │  calculate_emi(principal, annual_rate, tenure_yrs)  │  │
│  │  calculate_outstanding_principal(...)               │  │
│  │  calculate_new_emi_after_lump(...)                  │  │
│  └────────────────────────┬────────────────────────────┘  │
│                           │ called by                      │
│  ┌────────────────────────▼────────────────────────────┐  │
│  │  EMICalculator(QWidget)  — GUI Layer                │  │
│  │                                                     │  │
│  │  setup_dark_theme()  — QPalette configuration       │  │
│  │  init_ui()           — builds tabs, inputs, charts  │  │
│  │  on_calculate()      — validates input, calls funcs │  │
│  │  plot_graphs()       — renders matplotlib figures   │  │
│  └─────────────────────────────────────────────────────┘  │
│                                                           │
│  ┌─────────────────────────────────────────────────────┐  │
│  │  Entry Point:  if __name__ == "__main__"            │  │
│  │  QApplication → EMICalculator.show() → exec_()     │  │
│  └─────────────────────────────────────────────────────┘  │
└───────────────────────────────────────────────────────────┘
```

**Design decisions:**

- **Separation of concerns** — the three pure functions carry zero UI state and are individually testable.
- **Single-file simplicity** — the project is intentionally kept as one module to remain approachable.
- **PyQt5 + Matplotlib** — `FigureCanvasQTAgg` embeds the matplotlib figure directly into the Qt widget tree.

---

## 📂 File Structure

```
pyLoan/
├── pyLoan.py        ← Main application (GUI + calculation logic)
└── README.md        ← This file
```

---

## ⚙️ Installation

**Prerequisites:** Python 3.8 or newer.

```bash
# 1. Clone the repository
git clone https://github.com/Kaelith69/pyLoan.git
cd pyLoan

# 2. (Recommended) Create and activate a virtual environment
python -m venv .venv
source .venv/bin/activate      # macOS / Linux
.venv\Scripts\activate         # Windows

# 3. Install dependencies
pip install PyQt5 matplotlib numpy
```

> 💡 On some Linux distros you may also need the system Qt5 libraries:
> ```bash
> sudo apt-get install python3-pyqt5
> ```

---

## 🚀 Usage

```bash
python pyLoan.py
```

### Step-by-step walkthrough

```
1. Fill in "Loan Parameters":
   ┌──────────────────────────────────────┐
   │ Downpayment (₹):   200000            │
   │ Total Loan (₹):    2000000           │  ← principal = 1 800 000
   │ Interest Rate:     8.5               │  ← % per annum
   │ Tenure (years):    20                │
   └──────────────────────────────────────┘

2. (Optional) Fill "Lump-sum Prepayment":
   ┌──────────────────────────────────────┐
   │ Lump sum (₹):      300000            │
   │ At year (n):       5                 │
   └──────────────────────────────────────┘

3. Click  [ Calculate EMI ]

4. Results panel shows:
   Principal after downpayment: ₹18,00,000.00
   Monthly EMI:                 ₹15,620.82
   Total Payment:               ₹37,48,997.00
   Total Interest:              ₹19,48,997.00
   Interest to Principal Ratio: 108.28%

   After ₹3,00,000.00 at year 5:
   Remaining months: 180
   Revised EMI:      ₹12,543.11
   Total savings:    ₹3,71,844.60

5. Switch to the "Graphs" tab to see the three charts.
```

---

## 📐 Core API Reference

### `calculate_emi(principal, annual_rate, tenure_years)`

Calculates the fixed monthly instalment using the standard amortisation formula.

| Parameter | Type | Description |
|---|---|---|
| `principal` | `float` | Net loan amount (after downpayment), in ₹ |
| `annual_rate` | `float` | Annual interest rate, as a percentage (e.g. `8.5` for 8.5%) |
| `tenure_years` | `float` | Loan duration in years |

**Returns:** `float` — monthly EMI in ₹

**Formula:**

```
        P · r · (1 + r)^n
EMI = ─────────────────────
          (1 + r)^n − 1

where  r = annual_rate / 100 / 12   (monthly rate)
       n = int(tenure_years × 12)   (total months)
```

> When `annual_rate == 0`, the formula reduces to `EMI = P / n` (interest-free loan).

---

### `calculate_outstanding_principal(principal, annual_rate, tenure_years, paid_months)`

Returns the remaining principal balance after `paid_months` EMI payments.

| Parameter | Type | Description |
|---|---|---|
| `principal` | `float` | Original net loan amount |
| `annual_rate` | `float` | Annual interest rate (%) |
| `tenure_years` | `float` | Total loan tenure in years |
| `paid_months` | `int` | Number of EMI payments already made |

**Returns:** `float` — outstanding balance in ₹

---

### `calculate_new_emi_after_lump(principal, annual_rate, tenure_years, lump_sum, nth_year)`

Simulates a one-time lump-sum prepayment at the end of year `nth_year` and returns the recalculated EMI for the remaining term.

| Parameter | Type | Description |
|---|---|---|
| `principal` | `float` | Original net loan amount |
| `annual_rate` | `float` | Annual interest rate (%) |
| `tenure_years` | `float` | Total loan tenure in years |
| `lump_sum` | `float` | One-time prepayment amount in ₹ |
| `nth_year` | `int` | Year at which the lump sum is paid |

**Returns:** `float` — revised monthly EMI in ₹ (`0.0` if fully paid off)

---

## 📊 Visualizations

The **Graphs** tab renders three charts side-by-side using a `2×2` matplotlib grid:

```
┌──────────────────────┬──────────────────────┐
│  1. Payment Breakdown│  2. Outstanding       │
│     (Pie Chart)      │     Principal         │
│                      │     (Line Chart)      │
├──────────────────────┴──────────────────────┤
│  3. EMI Components Over Time                │
│     (Stacked Area Chart — Principal vs      │
│      Interest month by month)               │
└─────────────────────────────────────────────┘
```

| # | Chart | What it shows |
|---|---|---|
| 1 | **Payment Breakdown Pie** | Total principal vs total interest paid over the full term |
| 2 | **Outstanding Principal Curve** | How the loan balance decreases month-by-month |
| 3 | **EMI Components Stack** | The shifting ratio of principal/interest within each EMI payment |

---

## 🐛 Bug Fixes & Changelog

### v1.1.0 — Refactor & Bug-Fix Release

| # | Issue | Root Cause | Fix |
|---|---|---|---|
| 1 | **Division by zero — 0% interest rate** | `calculate_emi` computed `P·0·1 / (1−1)` → `ZeroDivisionError` | Added `if monthly_rate == 0: return P / n` branch |
| 2 | **Division by zero — 0% interest rate** | Same pattern in `calculate_outstanding_principal` | Added `if monthly_rate == 0` linear-interpolation branch |
| 3 | **Float `months` range in plots** | `np.arange(1, tenure * 12 + 1)` produced fractional steps when `tenure` was non-integer | Changed to `total_months = int(tenure * 12); np.arange(1, total_months + 1)` |
| 4 | **No guard for `tenure ≤ 0`** | Passing `tenure=0` would produce `total_months=0` and a divide-by-zero further down | Added explicit check in `on_calculate` with a user-facing warning |
| 5 | **No guard for `rate < 0`** | Negative rates produce meaningless / undefined results | Added to the same runtime validation block |

---

<div align="center">

*Built with ❤️ and Python · MIT License*

---

> 🤓 **Footer Dad Joke**
>
> *Why do Python developers make great loan officers?*
> *Because they always know how to handle **interest**ing exceptions!* 😄

</div>

