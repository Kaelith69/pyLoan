# pyLoan Wiki — Home

Welcome to the pyLoan wiki! This is your one-stop shop for everything you'd want to know about a desktop EMI calculator that fits in a single Python file.

If you're wondering "how complex can a loan calculator really be?" — come, sit down, let's talk about amortisation schedules.

---

## What Is pyLoan?

pyLoan is a **desktop Loan EMI (Equated Monthly Installment) calculator** built with Python, PyQt5, and Matplotlib. You run it locally, type in some numbers, and it tells you exactly how much money you're handing over to a bank across the life of your loan.

Spoiler: it's mostly interest. It's basically always interest.

---

## Quick Links

| Page | What It Covers |
|---|---|
| [Architecture](Architecture.md) | How the code is structured and why |
| [Installation](Installation.md) | Getting it running on your machine |
| [Usage](Usage.md) | Using the calculator, step by step |
| [Privacy](Privacy.md) | Why this app will never spy on you |
| [Troubleshooting](Troubleshooting.md) | When things go sideways |
| [Roadmap](Roadmap.md) | What might happen in the future |

---

## Tech Stack at a Glance

| Layer | Technology |
|---|---|
| GUI | PyQt5 (QWidget, QTabWidget, QGroupBox, QLineEdit) |
| Charts | Matplotlib via `FigureCanvasQTAgg` |
| Math | Pure Python + NumPy for array operations |
| Theme | QPalette dark mode + CSS-style Qt stylesheet |
| Entry Point | Standard `if __name__ == "__main__"` pattern |

---

## The Core Idea

1. User enters loan parameters (principal, rate, tenure)
2. App runs three pure math functions
3. Results render in a text panel
4. Three charts update in the Graphs tab

That's it. No magic. No AI. No blockchain. Just math.

---

## Contributing

Read [CONTRIBUTING.md](../CONTRIBUTING.md) in the root of the repo. PRs are welcome. Be excellent to each other.

---

*Last updated: 2026 · pyLoan v1.1.0*
