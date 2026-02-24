# Usage

You've installed it. Now what? This page walks you through everything the app can do — which is exactly what it says it does, nothing more, nothing less.

---

## Launching the App

```bash
python pyLoan.py
```

A window opens with two tabs: **Calculator** and **Graphs**.

---

## The Calculator Tab

### Loan Parameters (required)

| Field | What to Enter | Example |
|---|---|---|
| **Downpayment (₹)** | The upfront amount you're paying yourself | `200000` |
| **Total Loan (₹)** | The full property/item price | `2000000` |
| **Interest Rate (% p.a.)** | Annual interest rate as a percentage | `8.5` |
| **Tenure (years)** | Loan duration in years | `20` |

The **principal** used for calculations is: `Total Loan − Downpayment`.

So if your total loan is ₹20,00,000 and your downpayment is ₹2,00,000 — the app will calculate EMI on ₹18,00,000.

---

### Lump-Sum Prepayment (optional)

Have some extra cash burning a hole in your pocket? Use the prepayment section to simulate what happens when you make a one-time payment partway through your loan.

| Field | What to Enter | Example |
|---|---|---|
| **Lump sum (₹)** | Amount of the one-time prepayment | `300000` |
| **At year (n)** | The year you make the payment | `5` |

Leave these blank if you don't want a prepayment simulation.

---

### Clicking "Calculate EMI"

The results panel shows:

```
Principal after downpayment: ₹18,00,000.00
Monthly EMI:                 ₹15,620.82
Total Payment:               ₹37,48,997.00
Total Interest:              ₹19,48,997.00
Interest to Principal Ratio: 108.28%
```

If you filled in the lump-sum fields, you also get:

```
After ₹3,00,000.00 at year 5:
Remaining months: 180
Revised EMI:      ₹12,543.11
Total savings:    ₹3,71,844.60
```

The "Total savings" figure is: `(original total payment) − (amount paid before prepayment + lump sum + revised EMI × remaining months)`.

---

## The Graphs Tab

Switch to this tab after calculating to see three matplotlib charts:

### Chart 1 — Payment Breakdown (Pie)
Shows the split between total principal and total interest paid over the entire loan term. Stare at the interest slice and feel things.

### Chart 2 — Outstanding Principal (Line Chart)
Shows how your remaining loan balance decreases month by month. It curves — slowly at first (mostly interest), then faster as more of each payment goes to principal. This is amortisation doing its thing.

### Chart 3 — EMI Components Over Time (Stacked Area)
Shows the principal component vs interest component within each monthly payment across the full tenure. Early months: mostly interest (the bank is eating well). Later months: mostly principal (you're finally making progress). The crossover point is deeply satisfying to watch.

---

## The Math (For the Curious)

### EMI Formula

```
        P · r · (1 + r)^n
EMI = ─────────────────────
          (1 + r)^n − 1

where:
  P = principal (loan − downpayment)
  r = annual_rate / 100 / 12   (monthly rate)
  n = int(tenure_years × 12)   (total months)
```

**Special case:** If `annual_rate == 0`, this becomes `EMI = P / n`.

### Outstanding Balance Formula

```
                   P · ((1 + r)^n − (1 + r)^k)
Outstanding(k) = ─────────────────────────────────
                          (1 + r)^n − 1

where k = number of months already paid
```

### Lump-Sum Prepayment

1. Calculate outstanding balance at `nth_year × 12` months
2. Subtract the lump sum: `new_principal = outstanding − lump_sum`
3. Calculate new EMI using `new_principal` and `remaining_months = total_months − paid_months`

---

## Input Validation

The app validates your input in two ways:

1. **While typing** — `QDoubleValidator`/`QIntValidator` prevents non-numeric characters in fields
2. **On Calculate** — boundary checks catch:
   - `principal ≤ 0` (downpayment ≥ loan amount — you've already paid, congrats)
   - `rate < 0` (negative interest rates don't work here)
   - `tenure ≤ 0` (you can't repay a loan in zero years)

Invalid input shows a `QMessageBox` warning dialog with a description of what's wrong.

---

## Keyboard Tips

- **Tab** — move between input fields
- **Enter** — doesn't trigger Calculate (click the button or extend a PR to add it 👀)
- Standard text editing shortcuts work in all input fields

---

*[← Installation](Installation.md) · [Back to Home](Home.md) · [Troubleshooting →](Troubleshooting.md)*
