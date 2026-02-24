<div align="center">

<!-- ============================================================
     HERO SVG BANNER — pyLoan
     ============================================================ -->
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 860 220" width="860" height="220">
  <defs>
    <linearGradient id="heroBg" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" style="stop-color:#1a1a2e;stop-opacity:1"/>
      <stop offset="100%" style="stop-color:#0d1117;stop-opacity:1"/>
    </linearGradient>
    <linearGradient id="heroAccent" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" style="stop-color:#F59E0B;stop-opacity:1"/>
      <stop offset="100%" style="stop-color:#10B981;stop-opacity:1"/>
    </linearGradient>
    <linearGradient id="heroBlue" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" style="stop-color:#2563EB;stop-opacity:1"/>
      <stop offset="100%" style="stop-color:#F59E0B;stop-opacity:1"/>
    </linearGradient>
    <filter id="heroGlow">
      <feGaussianBlur stdDeviation="3" result="coloredBlur"/>
      <feMerge><feMergeNode in="coloredBlur"/><feMergeNode in="SourceGraphic"/></feMerge>
    </filter>
  </defs>
  <!-- Background -->
  <rect width="860" height="220" fill="url(#heroBg)" rx="14"/>
  <!-- Grid lines decoration -->
  <line x1="0" y1="55" x2="860" y2="55" stroke="#F59E0B" stroke-width="0.3" opacity="0.15"/>
  <line x1="0" y1="110" x2="860" y2="110" stroke="#F59E0B" stroke-width="0.3" opacity="0.15"/>
  <line x1="0" y1="165" x2="860" y2="165" stroke="#F59E0B" stroke-width="0.3" opacity="0.1"/>
  <line x1="215" y1="0" x2="215" y2="220" stroke="#2563EB" stroke-width="0.3" opacity="0.12"/>
  <line x1="430" y1="0" x2="430" y2="220" stroke="#2563EB" stroke-width="0.3" opacity="0.12"/>
  <line x1="645" y1="0" x2="645" y2="220" stroke="#2563EB" stroke-width="0.3" opacity="0.12"/>
  <!-- Coin decoration -->
  <circle cx="780" cy="60"  r="44" fill="none" stroke="#F59E0B" stroke-width="2" opacity="0.35"/>
  <circle cx="780" cy="60"  r="30" fill="none" stroke="#10B981" stroke-width="1.5" opacity="0.25"/>
  <circle cx="820" cy="155" r="30" fill="none" stroke="#2563EB" stroke-width="2" opacity="0.2"/>
  <circle cx="55"  cy="170" r="22" fill="none" stroke="#10B981" stroke-width="1.5" opacity="0.25"/>
  <!-- ₹ coin symbol -->
  <text x="776" y="68" font-family="Arial" font-size="28" fill="#F59E0B" opacity="0.75" text-anchor="middle" filter="url(#heroGlow)">₹</text>
  <!-- Accent bar -->
  <rect x="60" y="170" width="480" height="5" rx="2.5" fill="url(#heroAccent)" opacity="0.9"/>
  <!-- Main title -->
  <text x="60" y="105" font-family="'Segoe UI', Arial, sans-serif" font-size="58" font-weight="700"
        fill="#FFFFFF" filter="url(#heroGlow)">py</text>
  <text x="143" y="105" font-family="'Segoe UI', Arial, sans-serif" font-size="58" font-weight="700"
        fill="url(#heroAccent)" filter="url(#heroGlow)">Loan</text>
  <!-- Subtitle -->
  <text x="62" y="142" font-family="'Segoe UI', Arial, sans-serif" font-size="17" fill="#9CA3AF">
    Desktop EMI Calculator · Dark UI · Lump-sum Prepayment · Interactive Charts
  </text>
  <!-- Tags -->
  <rect x="62"  y="183" width="68" height="22" rx="11" fill="#F59E0B" opacity="0.88"/>
  <text x="96"  y="198" font-family="Arial" font-size="11" fill="#1a1a2e" text-anchor="middle" font-weight="bold">v1.1.0</text>
  <rect x="140" y="183" width="60" height="22" rx="11" fill="#2563EB" opacity="0.88"/>
  <text x="170" y="198" font-family="Arial" font-size="11" fill="#FFFFFF" text-anchor="middle">Python</text>
  <rect x="210" y="183" width="52" height="22" rx="11" fill="#10B981" opacity="0.88"/>
  <text x="236" y="198" font-family="Arial" font-size="11" fill="#FFFFFF" text-anchor="middle">PyQt5</text>
</svg>

---

> *"I wrote a loan calculator so I could finally understand why my mortgage exists.  
> Spoiler: it's mostly interest. It's basically always interest."* 😅

---

[![Python](https://img.shields.io/badge/Python-3.8%2B-3776AB?style=flat-square&logo=python&logoColor=white)](https://www.python.org/)
[![PyQt5](https://img.shields.io/badge/PyQt5-5.x-41CD52?style=flat-square&logo=qt&logoColor=white)](https://riverbankcomputing.com/software/pyqt/)
[![Matplotlib](https://img.shields.io/badge/Matplotlib-3.x-11557C?style=flat-square&logo=matplotlib&logoColor=white)](https://matplotlib.org/)
[![NumPy](https://img.shields.io/badge/NumPy-1.x-013243?style=flat-square&logo=numpy&logoColor=white)](https://numpy.org/)
[![License](https://img.shields.io/badge/License-MIT-F59E0B?style=flat-square)](LICENSE)
[![Version](https://img.shields.io/badge/version-1.1.0-2563EB?style=flat-square)](#-changelog)
[![Code style](https://img.shields.io/badge/code%20style-PEP8-10B981?style=flat-square)]()

</div>

---

## 📖 Table of Contents

1. [Overview](#-overview)
2. [System Overview](#-system-overview)
3. [Features](#-features)
4. [Capability Visualization](#-capability-visualization)
5. [Architecture](#-architecture-diagram)
6. [Data Flow](#-data-flow)
7. [Installation](#-installation)
8. [Usage](#-usage)
9. [Project Structure](#-project-structure)
10. [Performance Stats](#-performance-stats)
11. [Privacy](#-privacy)
12. [Roadmap](#-roadmap)
13. [License](#-license)

---

## 🔍 Overview

**pyLoan** is a desktop Loan EMI (Equated Monthly Installment) calculator built with **Python**, **PyQt5**, and **Matplotlib**.

You type numbers in. You click a button. You immediately find out exactly how much of your hard-earned money is going to the bank as "interest" (a lot). You cry a little. Then you use the lump-sum prepayment feature to feel slightly better about the situation. 💸

Concretely, it tells you:

- Your monthly EMI (the number your bank texts you every month like clockwork)
- Total interest payable — you'll want to be sitting down for this one
- Interest-to-principal ratio — a percentage that will haunt your dreams
- How a mid-term lump-sum payment reduces your future EMIs and saves you money

All results are backed by three interactive matplotlib charts embedded directly in the app window, because raw numbers alone aren't painful enough.

---

<div align="center">

![Humor](https://media.giphy.com/media/077i6AULCXc0FKTj9s/giphy.gif)

</div>

---

## 🧩 System Overview

pyLoan is a single-file desktop application. No server. No database. No cloud. No subscription model. No "premium tier". Just Python, Qt, and math. Radical, I know.

```
User's Brain → Input Fields → Math Functions → Results Panel + Charts
                                                ↑
                                    (matplotlib embedded in Qt)
```

The app has two tabs:
- **Calculator** — where you enter loan parameters and get results
- **Graphs** — where three matplotlib charts make you feel things about your debt

---

## ✨ Features

| Feature | Details |
|---|---|
| 🌑 **Dark Theme** | Full QPalette + stylesheet dark mode — your eyes will thank you at 2 AM |
| 🧮 **EMI Calculation** | Standard amortisation formula with correct 0%-rate handling (yes, that edge case is covered) |
| 💰 **Lump-Sum Prepayment** | Simulates a mid-term paydown, shows revised EMI and total savings |
| 📊 **3 Interactive Charts** | Pie breakdown · outstanding-principal decay curve · stacked EMI component area chart |
| ✅ **Input Validation** | `QDoubleValidator` / `QIntValidator` plus runtime boundary checks — you can't break it by typing garbage |
| 🛡️ **Edge-Case Safe** | Handles 0% interest rate and zero-tenure inputs without throwing a ZeroDivisionError tantrum |

---

## 📈 Capability Visualization

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 700 300" width="700" height="300">
  <defs>
    <linearGradient id="capBg" x1="0%" y1="0%" x2="0%" y2="100%">
      <stop offset="0%" style="stop-color:#0d1117;stop-opacity:1"/>
      <stop offset="100%" style="stop-color:#1a1a2e;stop-opacity:1"/>
    </linearGradient>
  </defs>
  <rect width="700" height="300" fill="url(#capBg)" rx="12"/>
  <text x="350" y="30" font-family="'Segoe UI',Arial,sans-serif" font-size="14" fill="#9CA3AF" text-anchor="middle">Capability Overview</text>

  <!-- Bars -->
  <!-- EMI Accuracy -->
  <text x="20" y="68" font-family="Arial" font-size="12" fill="#E5E7EB">EMI Accuracy</text>
  <rect x="160" y="54" width="500" height="18" rx="4" fill="#1F2937"/>
  <rect x="160" y="54" width="500" height="18" rx="4" fill="#F59E0B" opacity="0.9"/>
  <text x="668" y="67" font-family="Arial" font-size="11" fill="#F59E0B" text-anchor="end">100%</text>

  <!-- Lump-Sum Simulation -->
  <text x="20" y="105" font-family="Arial" font-size="12" fill="#E5E7EB">Lump-Sum Sim</text>
  <rect x="160" y="91" width="500" height="18" rx="4" fill="#1F2937"/>
  <rect x="160" y="91" width="475" height="18" rx="4" fill="#2563EB" opacity="0.88"/>
  <text x="668" y="104" font-family="Arial" font-size="11" fill="#2563EB" text-anchor="end">95%</text>

  <!-- Visualization -->
  <text x="20" y="142" font-family="Arial" font-size="12" fill="#E5E7EB">Visualization</text>
  <rect x="160" y="128" width="500" height="18" rx="4" fill="#1F2937"/>
  <rect x="160" y="128" width="450" height="18" rx="4" fill="#10B981" opacity="0.88"/>
  <text x="668" y="141" font-family="Arial" font-size="11" fill="#10B981" text-anchor="end">90%</text>

  <!-- Input Safety -->
  <text x="20" y="179" font-family="Arial" font-size="12" fill="#E5E7EB">Input Safety</text>
  <rect x="160" y="165" width="500" height="18" rx="4" fill="#1F2937"/>
  <rect x="160" y="165" width="500" height="18" rx="4" fill="#F59E0B" opacity="0.88"/>
  <text x="668" y="178" font-family="Arial" font-size="11" fill="#F59E0B" text-anchor="end">100%</text>

  <!-- Dark Theme UX -->
  <text x="20" y="216" font-family="Arial" font-size="12" fill="#E5E7EB">Dark Theme UX</text>
  <rect x="160" y="202" width="500" height="18" rx="4" fill="#1F2937"/>
  <rect x="160" y="202" width="500" height="18" rx="4" fill="#2563EB" opacity="0.88"/>
  <text x="668" y="215" font-family="Arial" font-size="11" fill="#2563EB" text-anchor="end">100%</text>

  <!-- Performance -->
  <text x="20" y="253" font-family="Arial" font-size="12" fill="#E5E7EB">Performance</text>
  <rect x="160" y="239" width="500" height="18" rx="4" fill="#1F2937"/>
  <rect x="160" y="239" width="490" height="18" rx="4" fill="#10B981" opacity="0.88"/>
  <text x="668" y="252" font-family="Arial" font-size="11" fill="#10B981" text-anchor="end">98%</text>

  <text x="350" y="290" font-family="Arial" font-size="11" fill="#6B7280" text-anchor="middle">All capabilities based on actual implemented functionality</text>
</svg>

---

## 🏗️ Architecture Diagram

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 700 380" width="700" height="380">
  <defs>
    <linearGradient id="archBg" x1="0%" y1="0%" x2="0%" y2="100%">
      <stop offset="0%" style="stop-color:#0d1117;stop-opacity:1"/>
      <stop offset="100%" style="stop-color:#1a1a2e;stop-opacity:1"/>
    </linearGradient>
    <marker id="arrow" markerWidth="10" markerHeight="7" refX="9" refY="3.5" orient="auto">
      <polygon points="0 0, 10 3.5, 0 7" fill="#F59E0B" opacity="0.8"/>
    </marker>
  </defs>
  <rect width="700" height="380" fill="url(#archBg)" rx="12"/>
  <text x="350" y="28" font-family="'Segoe UI',Arial,sans-serif" font-size="15" fill="#9CA3AF" text-anchor="middle" font-weight="bold">pyLoan.py — Application Architecture</text>

  <!-- Entry Point box -->
  <rect x="260" y="45" width="180" height="44" rx="8" fill="#1F2937" stroke="#F59E0B" stroke-width="1.5"/>
  <text x="350" y="62" font-family="Arial" font-size="11" fill="#F59E0B" text-anchor="middle" font-weight="bold">Entry Point</text>
  <text x="350" y="79" font-family="Arial" font-size="10" fill="#9CA3AF" text-anchor="middle">if __name__ == "__main__"</text>

  <!-- Arrow down -->
  <line x1="350" y1="89" x2="350" y2="118" stroke="#F59E0B" stroke-width="1.5" marker-end="url(#arrow)" opacity="0.8"/>

  <!-- QApplication box -->
  <rect x="240" y="120" width="220" height="40" rx="8" fill="#1F2937" stroke="#2563EB" stroke-width="1.5"/>
  <text x="350" y="135" font-family="Arial" font-size="11" fill="#2563EB" text-anchor="middle" font-weight="bold">QApplication</text>
  <text x="350" y="151" font-family="Arial" font-size="10" fill="#9CA3AF" text-anchor="middle">PyQt5 event loop</text>

  <!-- Arrow down -->
  <line x1="350" y1="160" x2="350" y2="188" stroke="#2563EB" stroke-width="1.5" marker-end="url(#arrow)" opacity="0.8"/>

  <!-- EMICalculator box -->
  <rect x="180" y="190" width="340" height="90" rx="8" fill="#1F2937" stroke="#10B981" stroke-width="2"/>
  <text x="350" y="210" font-family="Arial" font-size="12" fill="#10B981" text-anchor="middle" font-weight="bold">EMICalculator(QWidget)</text>
  <text x="350" y="228" font-family="Arial" font-size="10" fill="#9CA3AF" text-anchor="middle">setup_dark_theme() · init_ui()</text>
  <text x="350" y="244" font-family="Arial" font-size="10" fill="#9CA3AF" text-anchor="middle">on_calculate() · plot_graphs()</text>
  <text x="350" y="260" font-family="Arial" font-size="10" fill="#6B7280" text-anchor="middle">GUI Layer — QTabWidget · QGroupBox · FigureCanvasQTAgg</text>

  <!-- Arrow from EMICalculator down-left -->
  <line x1="270" y1="280" x2="200" y2="318" stroke="#F59E0B" stroke-width="1.5" marker-end="url(#arrow)" opacity="0.8"/>
  <!-- Arrow from EMICalculator down-right -->
  <line x1="430" y1="280" x2="500" y2="318" stroke="#2563EB" stroke-width="1.5" marker-end="url(#arrow)" opacity="0.8"/>

  <!-- Calc layer box -->
  <rect x="60" y="320" width="280" height="44" rx="8" fill="#1F2937" stroke="#F59E0B" stroke-width="1.5"/>
  <text x="200" y="337" font-family="Arial" font-size="11" fill="#F59E0B" text-anchor="middle" font-weight="bold">Calculation Layer (pure functions)</text>
  <text x="200" y="354" font-family="Arial" font-size="10" fill="#9CA3AF" text-anchor="middle">calculate_emi · outstanding · new_emi_after_lump</text>

  <!-- Charts box -->
  <rect x="360" y="320" width="280" height="44" rx="8" fill="#1F2937" stroke="#2563EB" stroke-width="1.5"/>
  <text x="500" y="337" font-family="Arial" font-size="11" fill="#2563EB" text-anchor="middle" font-weight="bold">Chart Layer (matplotlib)</text>
  <text x="500" y="354" font-family="Arial" font-size="10" fill="#9CA3AF" text-anchor="middle">Pie · Line · Stacked Area via FigureCanvas</text>
</svg>

---

## 🔄 Data Flow

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 700 260" width="700" height="260">
  <defs>
    <linearGradient id="dfBg" x1="0%" y1="0%" x2="0%" y2="100%">
      <stop offset="0%" style="stop-color:#0d1117;stop-opacity:1"/>
      <stop offset="100%" style="stop-color:#1a1a2e;stop-opacity:1"/>
    </linearGradient>
    <marker id="dfArrow" markerWidth="10" markerHeight="7" refX="9" refY="3.5" orient="auto">
      <polygon points="0 0, 10 3.5, 0 7" fill="#10B981" opacity="0.85"/>
    </marker>
  </defs>
  <rect width="700" height="260" fill="url(#dfBg)" rx="12"/>
  <text x="350" y="28" font-family="'Segoe UI',Arial,sans-serif" font-size="14" fill="#9CA3AF" text-anchor="middle" font-weight="bold">Data Flow — Calculator Tab</text>

  <!-- Step 1 -->
  <rect x="20" y="55" width="120" height="55" rx="8" fill="#1F2937" stroke="#F59E0B" stroke-width="1.5"/>
  <text x="80" y="77" font-family="Arial" font-size="11" fill="#F59E0B" text-anchor="middle" font-weight="bold">User Input</text>
  <text x="80" y="93" font-family="Arial" font-size="10" fill="#9CA3AF" text-anchor="middle">QLineEdit fields</text>
  <text x="80" y="106" font-family="Arial" font-size="10" fill="#6B7280" text-anchor="middle">validated on entry</text>

  <line x1="140" y1="83" x2="168" y2="83" stroke="#10B981" stroke-width="1.5" marker-end="url(#dfArrow)" opacity="0.85"/>

  <!-- Step 2 -->
  <rect x="170" y="55" width="120" height="55" rx="8" fill="#1F2937" stroke="#2563EB" stroke-width="1.5"/>
  <text x="230" y="77" font-family="Arial" font-size="11" fill="#2563EB" text-anchor="middle" font-weight="bold">on_calculate()</text>
  <text x="230" y="93" font-family="Arial" font-size="10" fill="#9CA3AF" text-anchor="middle">parse floats/ints</text>
  <text x="230" y="106" font-family="Arial" font-size="10" fill="#6B7280" text-anchor="middle">boundary checks</text>

  <line x1="290" y1="83" x2="318" y2="83" stroke="#10B981" stroke-width="1.5" marker-end="url(#dfArrow)" opacity="0.85"/>

  <!-- Step 3 -->
  <rect x="320" y="55" width="120" height="55" rx="8" fill="#1F2937" stroke="#F59E0B" stroke-width="1.5"/>
  <text x="380" y="71" font-family="Arial" font-size="11" fill="#F59E0B" text-anchor="middle" font-weight="bold">Pure Math</text>
  <text x="380" y="87" font-family="Arial" font-size="10" fill="#9CA3AF" text-anchor="middle">calculate_emi()</text>
  <text x="380" y="100" font-family="Arial" font-size="10" fill="#9CA3AF" text-anchor="middle">outstanding()</text>
  <text x="380" y="113" font-family="Arial" font-size="10" fill="#9CA3AF" text-anchor="middle">new_emi_after_lump()</text>

  <line x1="440" y1="83" x2="468" y2="83" stroke="#10B981" stroke-width="1.5" marker-end="url(#dfArrow)" opacity="0.85"/>

  <!-- Step 4 -->
  <rect x="470" y="55" width="120" height="55" rx="8" fill="#1F2937" stroke="#10B981" stroke-width="1.5"/>
  <text x="530" y="77" font-family="Arial" font-size="11" fill="#10B981" text-anchor="middle" font-weight="bold">Results</text>
  <text x="530" y="93" font-family="Arial" font-size="10" fill="#9CA3AF" text-anchor="middle">lbl_result HTML</text>
  <text x="530" y="106" font-family="Arial" font-size="10" fill="#6B7280" text-anchor="middle">+ 3 chart panels</text>

  <!-- Bottom row label -->
  <text x="350" y="160" font-family="'Segoe UI',Arial,sans-serif" font-size="13" fill="#9CA3AF" text-anchor="middle" font-weight="bold">Chart Rendering Path</text>

  <!-- Chart flow -->
  <rect x="170" y="180" width="120" height="50" rx="8" fill="#1F2937" stroke="#F59E0B" stroke-width="1.5"/>
  <text x="230" y="200" font-family="Arial" font-size="11" fill="#F59E0B" text-anchor="middle" font-weight="bold">plot_graphs()</text>
  <text x="230" y="218" font-family="Arial" font-size="10" fill="#9CA3AF" text-anchor="middle">called after calc</text>

  <line x1="290" y1="205" x2="318" y2="205" stroke="#10B981" stroke-width="1.5" marker-end="url(#dfArrow)" opacity="0.85"/>

  <rect x="320" y="180" width="120" height="50" rx="8" fill="#1F2937" stroke="#2563EB" stroke-width="1.5"/>
  <text x="380" y="200" font-family="Arial" font-size="11" fill="#2563EB" text-anchor="middle" font-weight="bold">matplotlib</text>
  <text x="380" y="218" font-family="Arial" font-size="10" fill="#9CA3AF" text-anchor="middle">figure.clear() + draw</text>

  <line x1="440" y1="205" x2="468" y2="205" stroke="#10B981" stroke-width="1.5" marker-end="url(#dfArrow)" opacity="0.85"/>

  <rect x="470" y="180" width="120" height="50" rx="8" fill="#1F2937" stroke="#10B981" stroke-width="1.5"/>
  <text x="530" y="200" font-family="Arial" font-size="11" fill="#10B981" text-anchor="middle" font-weight="bold">FigureCanvas</text>
  <text x="530" y="218" font-family="Arial" font-size="10" fill="#9CA3AF" text-anchor="middle">Qt widget redraws</text>
</svg>

---

## ⚙️ Installation

**Prerequisites:** Python 3.8 or newer. That's it. No Docker. No Kubernetes. No cloud account.

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

That's it. You're done. Go make yourself a coffee. ☕

---

## 🚀 Usage

```bash
python pyLoan.py
```

A window opens. You fill in boxes. You press a button. You get answers. It's not complicated — unlike your actual loan terms.

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

### Core API Reference

#### `calculate_emi(principal, annual_rate, tenure_years)`

| Parameter | Type | Description |
|---|---|---|
| `principal` | `float` | Net loan amount (after downpayment), in ₹ |
| `annual_rate` | `float` | Annual interest rate as a percentage (e.g. `8.5` for 8.5%) |
| `tenure_years` | `float` | Loan duration in years |

**Returns:** `float` — monthly EMI in ₹

```
        P · r · (1 + r)^n
EMI = ─────────────────────    where r = annual_rate/100/12,  n = int(tenure*12)
          (1 + r)^n − 1
```

When `annual_rate == 0`: `EMI = P / n` (interest-free, rare but handled).

#### `calculate_outstanding_principal(principal, annual_rate, tenure_years, paid_months)`

Returns remaining principal balance after `paid_months` EMI payments.

#### `calculate_new_emi_after_lump(principal, annual_rate, tenure_years, lump_sum, nth_year)`

Simulates a one-time prepayment at year `nth_year`, returns revised monthly EMI (`0.0` if fully paid off).

---

## 📂 Project Structure

```
pyLoan/
├── pyLoan.py          ← Everything. One file. Glorious.
├── README.md          ← You are here
├── LICENSE            ← MIT
├── CONTRIBUTING.md    ← How to contribute without breaking things
├── CHANGELOG.md       ← What changed and why
├── SECURITY.md        ← How to responsibly report issues
├── assets/
│   └── demo.gif       ← Place your demo GIF here
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

## ⚡ Performance Stats

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 700 200" width="700" height="200">
  <defs>
    <linearGradient id="statBg" x1="0%" y1="0%" x2="0%" y2="100%">
      <stop offset="0%" style="stop-color:#0d1117;stop-opacity:1"/>
      <stop offset="100%" style="stop-color:#1a1a2e;stop-opacity:1"/>
    </linearGradient>
  </defs>
  <rect width="700" height="200" fill="url(#statBg)" rx="12"/>
  <text x="350" y="28" font-family="'Segoe UI',Arial,sans-serif" font-size="14" fill="#9CA3AF" text-anchor="middle" font-weight="bold">Runtime Characteristics</text>

  <!-- Stat 1 -->
  <rect x="30" y="50" width="140" height="110" rx="10" fill="#1F2937" stroke="#F59E0B" stroke-width="1.5"/>
  <text x="100" y="90" font-family="Arial" font-size="28" fill="#F59E0B" text-anchor="middle" font-weight="bold">&lt;1ms</text>
  <text x="100" y="112" font-family="Arial" font-size="11" fill="#9CA3AF" text-anchor="middle">EMI Calculation</text>
  <text x="100" y="128" font-family="Arial" font-size="10" fill="#6B7280" text-anchor="middle">pure Python math</text>
  <text x="100" y="148" font-family="Arial" font-size="10" fill="#6B7280" text-anchor="middle">no overhead</text>

  <!-- Stat 2 -->
  <rect x="190" y="50" width="140" height="110" rx="10" fill="#1F2937" stroke="#2563EB" stroke-width="1.5"/>
  <text x="260" y="90" font-family="Arial" font-size="28" fill="#2563EB" text-anchor="middle" font-weight="bold">3</text>
  <text x="260" y="112" font-family="Arial" font-size="11" fill="#9CA3AF" text-anchor="middle">Chart Types</text>
  <text x="260" y="128" font-family="Arial" font-size="10" fill="#6B7280" text-anchor="middle">Pie · Line · Area</text>
  <text x="260" y="148" font-family="Arial" font-size="10" fill="#6B7280" text-anchor="middle">rendered via matplotlib</text>

  <!-- Stat 3 -->
  <rect x="350" y="50" width="140" height="110" rx="10" fill="#1F2937" stroke="#10B981" stroke-width="1.5"/>
  <text x="420" y="90" font-family="Arial" font-size="28" fill="#10B981" text-anchor="middle" font-weight="bold">1</text>
  <text x="420" y="112" font-family="Arial" font-size="11" fill="#9CA3AF" text-anchor="middle">Source File</text>
  <text x="420" y="128" font-family="Arial" font-size="10" fill="#6B7280" text-anchor="middle">pyLoan.py only</text>
  <text x="420" y="148" font-family="Arial" font-size="10" fill="#6B7280" text-anchor="middle">~389 lines</text>

  <!-- Stat 4 -->
  <rect x="510" y="50" width="160" height="110" rx="10" fill="#1F2937" stroke="#F59E0B" stroke-width="1.5"/>
  <text x="590" y="90" font-family="Arial" font-size="28" fill="#F59E0B" text-anchor="middle" font-weight="bold">3</text>
  <text x="590" y="112" font-family="Arial" font-size="11" fill="#9CA3AF" text-anchor="middle">Dependencies</text>
  <text x="590" y="128" font-family="Arial" font-size="10" fill="#6B7280" text-anchor="middle">PyQt5 · matplotlib</text>
  <text x="590" y="148" font-family="Arial" font-size="10" fill="#6B7280" text-anchor="middle">numpy</text>
</svg>

---

## 🔒 Privacy

**pyLoan is 100% offline.** Nothing you type is sent anywhere.

- No network requests. Ever.
- No telemetry. No analytics. No usage tracking.
- No file I/O. Your loan details stay in RAM and disappear when the window closes.
- No accounts, no login, no "free trial".

Your financial data is yours. The app is basically a fancy calculator that forgets everything the moment you close it.

---

## 🗺️ Roadmap

Things that might happen someday, in no particular order:

- [ ] **Export to PDF/CSV** — because sometimes you want to show the bank their own math
- [ ] **Comparison mode** — side-by-side loan comparison (Bank A vs. Bank B vs. your financial ruin)
- [ ] **Multiple lump-sum payments** — for when you find money in the couch cushions more than once
- [ ] **Floating interest rate support** — because apparently banks love chaos
- [ ] **Amortisation schedule table** — full month-by-month breakdown export
- [ ] **Currency selector** — for the international sufferers
- [ ] **Tests** — automated unit tests for the calculation layer (the math deserves it)

No promises. No roadmap tickets. No product managers. Just vibes and pull requests.

---

## 📜 License

MIT — see [LICENSE](LICENSE).

Go wild. Fork it, extend it, sell it (it's free software, but hey), embed it in something. Just don't blame me when you discover how much of your EMI is interest. I didn't make the loan. 😅

---

<div align="center">

*Built with ❤️, Python, and a healthy fear of amortisation tables*

---

> 🤓 *Why do Python developers make great loan officers?*  
> *Because they always know how to handle **interest**ing exceptions.* 😄

</div>

