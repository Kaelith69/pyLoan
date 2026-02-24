<div align="center">

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 860 220" width="860" height="220">
  <defs>
    <linearGradient id="heroBg" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" style="stop-color:#1a1200;stop-opacity:1"/>
      <stop offset="100%" style="stop-color:#0f1f10;stop-opacity:1"/>
    </linearGradient>
    <linearGradient id="heroAccent" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" style="stop-color:#F59E0B;stop-opacity:1"/>
      <stop offset="100%" style="stop-color:#10B981;stop-opacity:1"/>
    </linearGradient>
    <filter id="heroGlow">
      <feGaussianBlur stdDeviation="3" result="coloredBlur"/>
      <feMerge><feMergeNode in="coloredBlur"/><feMergeNode in="SourceGraphic"/></feMerge>
    </filter>
  </defs>
  <rect width="860" height="220" fill="url(#heroBg)" rx="14"/>
  <circle cx="780" cy="55"  r="44" fill="none" stroke="#F59E0B" stroke-width="2.5" opacity="0.35"/>
  <circle cx="780" cy="55"  r="30" fill="none" stroke="#10B981" stroke-width="1.5" opacity="0.25"/>
  <circle cx="820" cy="160" r="32" fill="none" stroke="#F59E0B" stroke-width="2" opacity="0.2"/>
  <circle cx="55"  cy="168" r="22" fill="none" stroke="#10B981" stroke-width="1.5" opacity="0.25"/>
  <circle cx="820" cy="55"  r="16" fill="#F59E0B" opacity="0.08"/>
  <text x="780" y="63" font-family="Arial, sans-serif" font-size="28" fill="#F59E0B" opacity="0.75" text-anchor="middle" filter="url(#heroGlow)">₹</text>
  <rect x="60" y="170" width="460" height="5" rx="2.5" fill="url(#heroAccent)" opacity="0.9"/>
  <text x="60" y="100" font-family="Arial, sans-serif" font-size="58" font-weight="700" fill="#FFFFFF" filter="url(#heroGlow)">py</text>
  <text x="145" y="100" font-family="Arial, sans-serif" font-size="58" font-weight="700" fill="url(#heroAccent)" filter="url(#heroGlow)">Loan</text>
  <text x="62" y="140" font-family="Arial, sans-serif" font-size="18" fill="#C0B090">Smart EMI Calculator · Dark UI · Interactive Graphs</text>
  <rect x="62" y="181" width="72" height="22" rx="11" fill="#F59E0B" opacity="0.9"/>
  <text x="98" y="196" font-family="Arial, sans-serif" font-size="12" fill="#1a1200" text-anchor="middle" font-weight="700">v1.1.0</text>
  <rect x="146" y="181" width="88" height="22" rx="11" fill="#10B981" opacity="0.9"/>
  <text x="190" y="196" font-family="Arial, sans-serif" font-size="12" fill="#FFFFFF" text-anchor="middle">Python 3.8+</text>
  <rect x="246" y="181" width="54" height="22" rx="11" fill="#2563EB" opacity="0.9"/>
  <text x="273" y="196" font-family="Arial, sans-serif" font-size="12" fill="#FFFFFF" text-anchor="middle">MIT</text>
</svg>

<br>

[![Python](https://img.shields.io/badge/Python-3.8%2B-3776AB?style=flat-square&logo=python&logoColor=white)](https://www.python.org/)
[![PyQt5](https://img.shields.io/badge/PyQt5-5.x-41CD52?style=flat-square&logo=qt&logoColor=white)](https://riverbankcomputing.com/software/pyqt/)
[![Matplotlib](https://img.shields.io/badge/Matplotlib-3.x-11557C?style=flat-square&logo=matplotlib&logoColor=white)](https://matplotlib.org/)
[![NumPy](https://img.shields.io/badge/NumPy-1.x-013243?style=flat-square&logo=numpy&logoColor=white)](https://numpy.org/)
[![License](https://img.shields.io/badge/License-MIT-F59E0B?style=flat-square)](LICENSE)
[![Version](https://img.shields.io/badge/version-1.1.0-10B981?style=flat-square)](#-changelog)
[![Code style](https://img.shields.io/badge/code%20style-PEP8-2563EB?style=flat-square)]()

</div>

---

> **The only financial advisor that doesn't charge you ₹5,000/hour for the privilege of staring at a spreadsheet.**
> pyLoan crunches your EMIs, simulates lump-sum prepayments, and renders three gorgeous dark-themed charts — all without a single cloud upload, subscription fee, or passive-aggressive "have you considered our premium tier?" pop-up.

<div align="center">

![Humor](https://media.giphy.com/media/3o7TKSjRrfIPjeiVyM/giphy.gif)

*pyLoan doing your amortisation math at 3 AM so you don't have to*

</div>

---

## 📖 Table of Contents

1. [System Overview](#-system-overview)
2. [Features](#-features)
3. [Architecture](#-architecture)
4. [Installation](#-installation)
5. [Usage](#-usage)
6. [Project Structure](#-project-structure)
7. [Core API Reference](#-core-api-reference)
8. [Privacy](#-privacy)
9. [Roadmap](#-roadmap)
10. [Changelog](#-changelog)
11. [License](#-license)

---

## 🔍 System Overview

**pyLoan** is a fully offline desktop Loan EMI (Equated Monthly Installment) calculator built with **Python**, **PyQt5**, and **Matplotlib**. It lives on your machine, respects your data, and never phones home. Think of it as the responsible adult version of opening Excel and Googling "EMI formula" at midnight.

**What it does in plain English:**

- Takes your loan details (amount, interest rate, tenure)
- Calculates your fixed monthly payment using the standard amortisation formula
- Optionally models a lump-sum prepayment mid-loan and tells you exactly how much you save
- Renders three matplotlib charts so you can *see* your money disappearing in real time (but make it aesthetic)

---

## ✨ Features

| Feature | Details |
|---|---|
| 🌑 **Dark Theme** | Full QPalette + QSS dark mode — because staring at a white screen at midnight is a form of self-harm |
| 🧮 **EMI Calculation** | Standard amortisation formula, including the `r=0` edge case that breaks most calculators |
| 💰 **Lump-Sum Prepayment** | Simulate dropping a windfall on your loan mid-term and see the revised EMI + total savings |
| 📊 **3 Interactive Charts** | Pie breakdown · Outstanding-principal curve · Stacked EMI components |
| ✅ **Input Validation** | `QDoubleValidator` / `QIntValidator` plus runtime boundary checks — garbage in, helpful error out |
| 🛡️ **Edge-Case Safe** | Handles 0% interest, zero tenure, negative rates, and loans fully covered by a lump sum |
| 🖥️ **100% Offline** | No telemetry, no API calls, no accounts. Your bank details stay on your machine |

<br>

<div align="center">

<!-- SVG: CAPABILITY GRAPH -->
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 700 310" width="700" height="310">
  <defs>
    <linearGradient id="capBg" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" style="stop-color:#1a1200;stop-opacity:1"/>
      <stop offset="100%" style="stop-color:#0d1a0e;stop-opacity:1"/>
    </linearGradient>
    <linearGradient id="bar1" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" style="stop-color:#F59E0B;stop-opacity:1"/>
      <stop offset="100%" style="stop-color:#FBBF24;stop-opacity:0.8"/>
    </linearGradient>
    <linearGradient id="bar2" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" style="stop-color:#10B981;stop-opacity:1"/>
      <stop offset="100%" style="stop-color:#34D399;stop-opacity:0.8"/>
    </linearGradient>
    <linearGradient id="bar3" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" style="stop-color:#2563EB;stop-opacity:1"/>
      <stop offset="100%" style="stop-color:#3B82F6;stop-opacity:0.8"/>
    </linearGradient>
  </defs>
  <rect width="700" height="310" fill="url(#capBg)" rx="12"/>
  <text x="350" y="36" font-family="Arial, sans-serif" font-size="16" font-weight="700" fill="#F59E0B" text-anchor="middle">Capability Overview</text>
  <!-- Row labels -->
  <text x="24" y="82"  font-family="Arial, sans-serif" font-size="12" fill="#C0B090">EMI Accuracy</text>
  <text x="24" y="122" font-family="Arial, sans-serif" font-size="12" fill="#C0B090">Prepayment Sim</text>
  <text x="24" y="162" font-family="Arial, sans-serif" font-size="12" fill="#C0B090">Visualisation</text>
  <text x="24" y="202" font-family="Arial, sans-serif" font-size="12" fill="#C0B090">Input Validation</text>
  <text x="24" y="242" font-family="Arial, sans-serif" font-size="12" fill="#C0B090">Edge-Case Safety</text>
  <text x="24" y="282" font-family="Arial, sans-serif" font-size="12" fill="#C0B090">Offline Privacy</text>
  <!-- Track backgrounds -->
  <rect x="185" y="66"  width="460" height="20" rx="10" fill="#2a2000" opacity="0.8"/>
  <rect x="185" y="106" width="460" height="20" rx="10" fill="#2a2000" opacity="0.8"/>
  <rect x="185" y="146" width="460" height="20" rx="10" fill="#2a2000" opacity="0.8"/>
  <rect x="185" y="186" width="460" height="20" rx="10" fill="#2a2000" opacity="0.8"/>
  <rect x="185" y="226" width="460" height="20" rx="10" fill="#2a2000" opacity="0.8"/>
  <rect x="185" y="266" width="460" height="20" rx="10" fill="#2a2000" opacity="0.8"/>
  <!-- Filled bars -->
  <rect x="185" y="66"  width="437" height="20" rx="10" fill="url(#bar1)"/>
  <rect x="185" y="106" width="391" height="20" rx="10" fill="url(#bar2)"/>
  <rect x="185" y="146" width="414" height="20" rx="10" fill="url(#bar3)"/>
  <rect x="185" y="186" width="437" height="20" rx="10" fill="url(#bar1)"/>
  <rect x="185" y="226" width="460" height="20" rx="10" fill="url(#bar2)"/>
  <rect x="185" y="266" width="460" height="20" rx="10" fill="url(#bar3)"/>
  <!-- Percentage labels -->
  <text x="632" y="81"  font-family="Arial, sans-serif" font-size="11" fill="#FFFFFF" font-weight="700">95%</text>
  <text x="586" y="121" font-family="Arial, sans-serif" font-size="11" fill="#FFFFFF" font-weight="700">85%</text>
  <text x="609" y="161" font-family="Arial, sans-serif" font-size="11" fill="#FFFFFF" font-weight="700">90%</text>
  <text x="632" y="201" font-family="Arial, sans-serif" font-size="11" fill="#FFFFFF" font-weight="700">95%</text>
  <text x="655" y="241" font-family="Arial, sans-serif" font-size="11" fill="#FFFFFF" font-weight="700">100%</text>
  <text x="655" y="281" font-family="Arial, sans-serif" font-size="11" fill="#FFFFFF" font-weight="700">100%</text>
</svg>

</div>

---

## 🏗️ Architecture

pyLoan follows a clean two-layer separation: a **pure calculation engine** (plain Python functions, zero Qt dependency) and a **GUI layer** (PyQt5 + embedded Matplotlib). This means you can unit-test the math without ever touching a display.

<div align="center">

<!-- SVG: ARCHITECTURE DIAGRAM -->
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 700 380" width="700" height="380">
  <defs>
    <linearGradient id="archBg" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" style="stop-color:#1a1200;stop-opacity:1"/>
      <stop offset="100%" style="stop-color:#0d1a0e;stop-opacity:1"/>
    </linearGradient>
  </defs>
  <rect width="700" height="380" fill="url(#archBg)" rx="12"/>
  <text x="350" y="32" font-family="Arial, sans-serif" font-size="16" font-weight="700" fill="#F59E0B" text-anchor="middle">pyLoan Architecture</text>
  <!-- Outer file box -->
  <rect x="30" y="48" width="640" height="310" rx="10" fill="none" stroke="#F59E0B" stroke-width="1.5" opacity="0.5"/>
  <text x="50" y="68" font-family="Arial, sans-serif" font-size="12" fill="#F59E0B" opacity="0.7">pyLoan.py</text>
  <!-- Calculation layer box -->
  <rect x="60" y="80" width="580" height="100" rx="8" fill="#1e1600" stroke="#10B981" stroke-width="1.5"/>
  <text x="350" y="100" font-family="Arial, sans-serif" font-size="13" font-weight="700" fill="#10B981" text-anchor="middle">Calculation Engine (Pure Python)</text>
  <text x="350" y="122" font-family="Arial, sans-serif" font-size="11" fill="#A0C0A0" text-anchor="middle">calculate_emi(principal, annual_rate, tenure_years)</text>
  <text x="350" y="140" font-family="Arial, sans-serif" font-size="11" fill="#A0C0A0" text-anchor="middle">calculate_outstanding_principal(principal, annual_rate, tenure_years, paid_months)</text>
  <text x="350" y="158" font-family="Arial, sans-serif" font-size="11" fill="#A0C0A0" text-anchor="middle">calculate_new_emi_after_lump(principal, annual_rate, tenure_years, lump_sum, nth_year)</text>
  <!-- Arrow down -->
  <line x1="350" y1="180" x2="350" y2="208" stroke="#F59E0B" stroke-width="2"/>
  <polygon points="342,205 350,220 358,205" fill="#F59E0B"/>
  <text x="370" y="198" font-family="Arial, sans-serif" font-size="10" fill="#F59E0B">called by</text>
  <!-- GUI layer box -->
  <rect x="60" y="220" width="580" height="110" rx="8" fill="#1e1600" stroke="#2563EB" stroke-width="1.5"/>
  <text x="350" y="240" font-family="Arial, sans-serif" font-size="13" font-weight="700" fill="#2563EB" text-anchor="middle">EMICalculator(QWidget) — GUI Layer</text>
  <text x="140" y="262" font-family="Arial, sans-serif" font-size="11" fill="#A0B0D0">setup_dark_theme()</text>
  <text x="320" y="262" font-family="Arial, sans-serif" font-size="11" fill="#A0B0D0">init_ui()</text>
  <text x="140" y="282" font-family="Arial, sans-serif" font-size="11" fill="#A0B0D0">on_calculate()</text>
  <text x="320" y="282" font-family="Arial, sans-serif" font-size="11" fill="#A0B0D0">plot_graphs()</text>
  <text x="350" y="310" font-family="Arial, sans-serif" font-size="11" fill="#7090B0" text-anchor="middle">PyQt5 (widgets, layout, validators) + Matplotlib FigureCanvasQTAgg</text>
  <!-- Entry point box -->
  <rect x="200" y="346" width="300" height="26" rx="6" fill="#1e1600" stroke="#F59E0B" stroke-width="1" opacity="0.8"/>
  <text x="350" y="363" font-family="Arial, sans-serif" font-size="11" fill="#F59E0B" text-anchor="middle">Entry Point: QApplication → show() → exec_()</text>
</svg>

</div>

**Design decisions:**

- **Separation of concerns** — the three pure functions carry zero UI state and are individually testable with plain `assert` statements.
- **Single-file simplicity** — intentionally one module to stay approachable. No frameworks, no magic imports, no 47-layer dependency tree.
- **PyQt5 + Matplotlib** — `FigureCanvasQTAgg` embeds matplotlib directly into the Qt widget tree. No web views, no subprocess rendering.

---

## ⚙️ Installation

**Prerequisites:** Python 3.8+. That's it. No Docker. No cloud. No Skynet. Relax.

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

> 💡 **Linux users:** Some distros need the system Qt5 libraries too:
> ```bash
> sudo apt-get install python3-pyqt5
> ```

> 💡 **macOS users:** If you hit SSL certificate errors, run `pip install --upgrade certifi` first. Not our fault — blame the snake.

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

<br>

<div align="center">

<!-- SVG: DATA FLOW DIAGRAM -->
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 700 200" width="700" height="200">
  <defs>
    <linearGradient id="dfBg" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" style="stop-color:#1a1200;stop-opacity:1"/>
      <stop offset="100%" style="stop-color:#0d1a0e;stop-opacity:1"/>
    </linearGradient>
  </defs>
  <rect width="700" height="200" fill="url(#dfBg)" rx="12"/>
  <text x="350" y="28" font-family="Arial, sans-serif" font-size="15" font-weight="700" fill="#F59E0B" text-anchor="middle">Data Flow</text>
  <!-- Box 1: User Input -->
  <rect x="20" y="55" width="110" height="60" rx="8" fill="#1e1600" stroke="#F59E0B" stroke-width="1.5"/>
  <text x="75" y="80" font-family="Arial, sans-serif" font-size="11" font-weight="700" fill="#F59E0B" text-anchor="middle">User Input</text>
  <text x="75" y="98" font-family="Arial, sans-serif" font-size="10" fill="#A0A070" text-anchor="middle">QLineEdit fields</text>
  <!-- Arrow -->
  <line x1="130" y1="85" x2="158" y2="85" stroke="#F59E0B" stroke-width="2"/>
  <polygon points="155,79 168,85 155,91" fill="#F59E0B"/>
  <!-- Box 2: Validation -->
  <rect x="168" y="55" width="110" height="60" rx="8" fill="#1e1600" stroke="#10B981" stroke-width="1.5"/>
  <text x="223" y="80" font-family="Arial, sans-serif" font-size="11" font-weight="700" fill="#10B981" text-anchor="middle">Validation</text>
  <text x="223" y="98" font-family="Arial, sans-serif" font-size="10" fill="#A0C0A0" text-anchor="middle">on_calculate()</text>
  <!-- Arrow -->
  <line x1="278" y1="85" x2="306" y2="85" stroke="#10B981" stroke-width="2"/>
  <polygon points="303,79 316,85 303,91" fill="#10B981"/>
  <!-- Box 3: Calculation -->
  <rect x="316" y="55" width="120" height="60" rx="8" fill="#1e1600" stroke="#2563EB" stroke-width="1.5"/>
  <text x="376" y="75" font-family="Arial, sans-serif" font-size="11" font-weight="700" fill="#2563EB" text-anchor="middle">Calculation</text>
  <text x="376" y="91" font-family="Arial, sans-serif" font-size="10" fill="#A0B0D0" text-anchor="middle">calculate_emi()</text>
  <text x="376" y="107" font-family="Arial, sans-serif" font-size="10" fill="#A0B0D0" text-anchor="middle">outstanding / lump</text>
  <!-- Arrow -->
  <line x1="436" y1="85" x2="464" y2="85" stroke="#2563EB" stroke-width="2"/>
  <polygon points="461,79 474,85 461,91" fill="#2563EB"/>
  <!-- Box 4: Display -->
  <rect x="474" y="55" width="110" height="60" rx="8" fill="#1e1600" stroke="#F59E0B" stroke-width="1.5"/>
  <text x="529" y="75" font-family="Arial, sans-serif" font-size="11" font-weight="700" fill="#F59E0B" text-anchor="middle">Display</text>
  <text x="529" y="91" font-family="Arial, sans-serif" font-size="10" fill="#A0A070" text-anchor="middle">QLabel results</text>
  <text x="529" y="107" font-family="Arial, sans-serif" font-size="10" fill="#A0A070" text-anchor="middle">+ plot_graphs()</text>
  <!-- Error path -->
  <line x1="223" y1="115" x2="223" y2="148" stroke="#EF4444" stroke-width="1.5" stroke-dasharray="4,3"/>
  <polygon points="217,145 223,158 229,145" fill="#EF4444"/>
  <rect x="160" y="158" width="126" height="26" rx="6" fill="#1e1600" stroke="#EF4444" stroke-width="1"/>
  <text x="223" y="175" font-family="Arial, sans-serif" font-size="10" fill="#EF4444" text-anchor="middle">QMessageBox warning</text>
</svg>

</div>

---

## 📂 Project Structure

```
pyLoan/
├── pyLoan.py          ← Entire application: calculation engine + GUI
├── README.md          ← You are here
├── LICENSE            ← MIT License
├── CONTRIBUTING.md    ← How to contribute without losing your mind
├── CHANGELOG.md       ← What changed, and why
├── SECURITY.md        ← How to report vulnerabilities
└── docs/
    └── wiki/
        ├── Home.md
        ├── Architecture.md
        ├── Installation.md
        ├── Usage.md
        ├── Privacy.md
        ├── Troubleshooting.md
        └── Roadmap.md
```

---

## 📐 Core API Reference

### `calculate_emi(principal, annual_rate, tenure_years)`

Calculates the fixed monthly instalment using the standard amortisation formula.

| Parameter | Type | Description |
|---|---|---|
| `principal` | `float` | Net loan amount (after downpayment), in ₹ |
| `annual_rate` | `float` | Annual interest rate as a percentage (e.g. `8.5`) |
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

> When `annual_rate == 0`, reduces to `EMI = P / n` (interest-free loan).

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

Simulates a one-time lump-sum prepayment at end of year `nth_year` and returns the recalculated EMI for the remaining term.

| Parameter | Type | Description |
|---|---|---|
| `principal` | `float` | Original net loan amount |
| `annual_rate` | `float` | Annual interest rate (%) |
| `tenure_years` | `float` | Total loan tenure in years |
| `lump_sum` | `float` | One-time prepayment amount in ₹ |
| `nth_year` | `int` | Year at which the lump sum is paid |

**Returns:** `float` — revised monthly EMI in ₹ (`0.0` if fully paid off)

---

<div align="center">

<!-- SVG: STATS VISUALIZATION -->
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 700 180" width="700" height="180">
  <defs>
    <linearGradient id="statsBg" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" style="stop-color:#1a1200;stop-opacity:1"/>
      <stop offset="100%" style="stop-color:#0d1a0e;stop-opacity:1"/>
    </linearGradient>
  </defs>
  <rect width="700" height="180" fill="url(#statsBg)" rx="12"/>
  <text x="350" y="30" font-family="Arial, sans-serif" font-size="15" font-weight="700" fill="#F59E0B" text-anchor="middle">pyLoan by the Numbers</text>
  <!-- Stat 1 -->
  <rect x="30" y="52" width="140" height="90" rx="10" fill="#1e1600" stroke="#F59E0B" stroke-width="1.5"/>
  <text x="100" y="88" font-family="Arial, sans-serif" font-size="28" font-weight="700" fill="#F59E0B" text-anchor="middle">1B</text>
  <text x="100" y="106" font-family="Arial, sans-serif" font-size="11" fill="#C0B090" text-anchor="middle">Max Loan (₹)</text>
  <text x="100" y="124" font-family="Arial, sans-serif" font-size="10" fill="#807060" text-anchor="middle">yes, billion</text>
  <!-- Stat 2 -->
  <rect x="190" y="52" width="140" height="90" rx="10" fill="#1e1600" stroke="#10B981" stroke-width="1.5"/>
  <text x="260" y="88" font-family="Arial, sans-serif" font-size="28" font-weight="700" fill="#10B981" text-anchor="middle">100</text>
  <text x="260" y="106" font-family="Arial, sans-serif" font-size="11" fill="#A0C0A0" text-anchor="middle">Max Tenure (years)</text>
  <text x="260" y="124" font-family="Arial, sans-serif" font-size="10" fill="#607060" text-anchor="middle">longer than mortgages</text>
  <!-- Stat 3 -->
  <rect x="350" y="52" width="140" height="90" rx="10" fill="#1e1600" stroke="#2563EB" stroke-width="1.5"/>
  <text x="420" y="88" font-family="Arial, sans-serif" font-size="28" font-weight="700" fill="#2563EB" text-anchor="middle">3</text>
  <text x="420" y="106" font-family="Arial, sans-serif" font-size="11" fill="#A0B0D0" text-anchor="middle">Live Charts</text>
  <text x="420" y="124" font-family="Arial, sans-serif" font-size="10" fill="#607090" text-anchor="middle">renders on calculate</text>
  <!-- Stat 4 -->
  <rect x="510" y="52" width="160" height="90" rx="10" fill="#1e1600" stroke="#F59E0B" stroke-width="1.5"/>
  <text x="590" y="88" font-family="Arial, sans-serif" font-size="28" font-weight="700" fill="#F59E0B" text-anchor="middle">0</text>
  <text x="590" y="106" font-family="Arial, sans-serif" font-size="11" fill="#C0B090" text-anchor="middle">Cloud Uploads</text>
  <text x="590" y="124" font-family="Arial, sans-serif" font-size="10" fill="#807060" text-anchor="middle">your data stays local</text>
</svg>

</div>

---

## 🔒 Privacy

**pyLoan is 100% offline.** It does not:

- Connect to the internet
- Send any data anywhere
- Require an account, email, or phone number
- Use analytics, telemetry, or crash reporters
- Store your loan data after the window closes

Your financial inputs live in memory for the duration of the session and nowhere else. Close the window, they're gone. No logs, no files, no surprises.

---

## 🗺️ Roadmap

| Status | Feature |
|---|---|
| ✅ Done | EMI calculation with 0%-rate edge case |
| ✅ Done | Lump-sum prepayment simulation |
| ✅ Done | 3 dark-themed matplotlib charts |
| ✅ Done | Input validation and runtime boundary checks |
| 🔜 Planned | Export results to PDF / CSV |
| 🔜 Planned | Multiple loan comparison mode |
| 🔜 Planned | Floating-rate (ARM) loan simulation |
| 🔜 Planned | Loan prepayment schedule table |
| 💡 Idea | Currency selector (beyond ₹) |
| 💡 Idea | Localisation (i18n) |

---

## 🐛 Changelog

### v1.1.0 — Refactor & Bug-Fix Release

| # | Issue | Root Cause | Fix |
|---|---|---|---|
| 1 | **Division by zero — 0% interest** | `calculate_emi` computed `P·0·1 / (1−1)` → `ZeroDivisionError` | Added `if monthly_rate == 0: return P / n` branch |
| 2 | **Division by zero — 0% interest** | Same pattern in `calculate_outstanding_principal` | Added matching `if monthly_rate == 0` branch |
| 3 | **Float month range in plots** | `np.arange` with non-integer `tenure` produced fractional month indices | Changed to `int(tenure * 12)` before range |
| 4 | **No guard for `tenure ≤ 0`** | Zero tenure → `total_months=0` → downstream divide-by-zero | Runtime check in `on_calculate` with user warning |
| 5 | **No guard for `rate < 0`** | Negative rates produce undefined results | Added to same runtime validation block |

### v1.0.0 — Initial Release

- Basic EMI calculator with PyQt5 dark theme
- Lump-sum prepayment field
- Matplotlib charts embedded via `FigureCanvasQTAgg`

---

## 📄 License

MIT — see [LICENSE](LICENSE). Use it, fork it, ship it. Just don't blame us if your bank disagrees with the math.

---

<div align="center">

*Built with ❤️, Python, and the kind of financial anxiety that only a mortgage can produce.*

---

> 🤓 *Why do Python developers make great loan officers?*
> *Because they always know how to handle **interest**ing exceptions.*

</div>

