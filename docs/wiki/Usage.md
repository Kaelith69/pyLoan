# Usage

How to use pyLoan without reading the entire source code first.

---

## Launching the App

```bash
python pyLoan.py
```

A dark-themed window opens with two tabs: **Calculator** and **Graphs**.

---

## The Calculator Tab

### Loan Parameters (Required)

| Field | What to enter | Example |
|---|---|---|
| Downpayment (₹) | The amount you're paying upfront | `200000` |
| Total Loan (₹) | The full property / asset price | `2000000` |
| Interest Rate (% p.a.) | Annual interest rate as a percentage | `8.5` |
| Tenure (years) | Loan duration in years (decimals OK) | `20` |

The **principal** pyLoan calculates against is `Total Loan − Downpayment`. So in the example above: `2,000,000 − 200,000 = ₹18,00,000`.

### Lump-Sum Prepayment (Optional)

If you're planning to drop a lump sum mid-loan (bonus, inheritance, "I found money in a drawer"), fill these in:

| Field | What to enter | Example |
|---|---|---|
| Lump sum (₹) | The one-time prepayment amount | `300000` |
| At year (n) | The year at which you'll make the payment | `5` |

Leave these blank (or at `0`) to skip the prepayment simulation.

---

## Clicking "Calculate EMI"

Hit the **Calculate EMI** button. The results panel below it updates instantly.

### Sample Output

```
Principal after downpayment: ₹18,00,000.00
Monthly EMI:                 ₹15,620.82
Total Payment:               ₹37,48,997.00
Total Interest:              ₹19,48,997.00
Interest to Principal Ratio: 108.28%

After ₹3,00,000.00 at year 5:
Remaining months: 180
Revised EMI:      ₹12,543.11
Total savings:    ₹3,71,844.60
```

### What Each Line Means

- **Principal after downpayment** — the net amount you're actually borrowing.
- **Monthly EMI** — your fixed monthly payment for the full tenure.
- **Total Payment** — what you'll pay in total over the life of the loan (principal + all interest).
- **Total Interest** — the difference between total payment and principal. The bank's cut. Try not to cry.
- **Interest to Principal Ratio** — how much interest you're paying relative to what you borrowed. Over 100% means you pay back more than double what you borrowed. Welcome to mortgages.
- **Revised EMI** — your new monthly payment after the lump sum reduces the outstanding principal.
- **Total savings** — the difference between the original total payment and the new total payment (including the lump sum itself). Money you didn't give to the bank.

---

## The Graphs Tab

Switch to the **Graphs** tab after calculating to see three charts:

### Chart 1 — Payment Breakdown (Pie)

Shows the split between total principal and total interest over the full loan term. If the interest slice is bigger than the principal slice, that's normal. That's also why banks exist.

### Chart 2 — Outstanding Principal Over Time (Line)

Shows how your remaining loan balance decreases month by month. Notice it starts slow? That's because early payments are mostly interest. Yes, really.

### Chart 3 — EMI Components Over Time (Stacked Area)

Shows how the composition of each monthly payment shifts over time. Early payments are mostly interest (top, lighter area). Later payments are mostly principal (bottom, darker area). This is the amortisation schedule visualised.

---

## Input Validation

pyLoan validates all inputs before calculating:

- Non-numeric input is blocked at the field level by `QDoubleValidator` / `QIntValidator`.
- `Total Loan ≤ Downpayment` → "No loan after downpayment" message (not an error — just done).
- `Rate < 0` → warning dialog.
- `Tenure ≤ 0` → warning dialog.
- Any unparseable numeric field → "Please enter valid numeric values" dialog.

The lump-sum fields are optional — leaving them empty treats them as `0`.

---

## Keyboard Shortcuts

pyLoan doesn't have custom keyboard shortcuts (yet), but standard Qt shortcuts work:

- `Tab` — move between fields
- `Enter` — trigger the focused button

---

## Edge Cases Worth Knowing

| Scenario | Result |
|---|---|
| `Interest rate = 0%` | EMI = Principal ÷ Total Months (interest-free calculation) |
| Lump sum ≥ outstanding principal at year N | "Your lump-sum fully paid off the remaining loan!" |
| Non-integer tenure (e.g., 2.5 years) | Handled correctly; charts use integer month counts |
| Downpayment = Total Loan | "No loan after downpayment" — not an error |
