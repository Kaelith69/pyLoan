# Roadmap

Where pyLoan is going — and at what pace.

---

## Current State (v1.1.0)

The core is solid. EMI calculations are correct across edge cases (0% interest, lump-sum prepayment, non-integer tenures). The UI is clean, dark-themed, and ships three matplotlib charts. The calculation engine is fully separated from the GUI and testable independently.

This is a good foundation. Here's what's next.

---

## Planned Features

### 🔜 Near-term

| Feature | Description | Status |
|---|---|---|
| **PDF / CSV Export** | Export the full amortisation schedule and summary to a PDF or CSV file without leaving the app | Planned |
| **Amortisation Schedule Table** | A scrollable table showing month-by-month principal, interest, and outstanding balance | Planned |
| **Multiple Loan Comparison** | Side-by-side comparison of 2–3 loan scenarios with different rates or tenures | Planned |

### 🗓️ Medium-term

| Feature | Description | Status |
|---|---|---|
| **Floating-Rate (ARM) Simulation** | Model loans where the interest rate changes at defined intervals | Idea |
| **Prepayment Schedule** | Instead of a one-time lump sum, model multiple prepayments spread over the loan term | Idea |
| **Currency Selector** | Switch the currency symbol from ₹ to $, €, £, etc. without affecting calculations | Idea |

### 💡 Long-term / Exploratory

| Feature | Description | Status |
|---|---|---|
| **Localisation (i18n)** | UI strings in multiple languages | Exploratory |
| **Dark/Light Theme Toggle** | Some people genuinely prefer white backgrounds. We don't judge. | Exploratory |
| **Loan Affordability Calculator** | "Given my monthly budget of ₹X, what loan can I afford?" — reverse EMI calculation | Exploratory |

---

## What's NOT on the Roadmap

To be clear about scope:

- **Cloud sync / account system** — pyLoan is and will remain 100% offline. Data sovereignty matters.
- **Mobile app** — This is a desktop tool. Use a browser-based calculator on mobile.
- **Bank API integration** — Fetching live rates is outside scope and would require internet access.
- **Machine learning / AI features** — It's a calculator. It already knows the math.

---

## How to Influence the Roadmap

Open a [GitHub Issue](https://github.com/Kaelith69/pyLoan/issues) with a feature request. Describe the use case, not just the feature — "I want PDF export because I need to share results with my financial advisor" is more useful than "add PDF export."

If you want to build something on the roadmap yourself, check [CONTRIBUTING.md](../../CONTRIBUTING.md) and open a PR. We'd rather review working code than argue about whether a feature is worth doing.

---

## Release Philosophy

pyLoan uses [Semantic Versioning](https://semver.org/):

- **Patch (1.1.x)** — bug fixes and minor internal improvements
- **Minor (1.x.0)** — new features that are backward compatible
- **Major (x.0.0)** — breaking changes (unlikely given the project scope)

Releases happen when features are ready, not on a fixed schedule. Quality over velocity.
