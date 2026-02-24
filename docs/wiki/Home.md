<div align="center">

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 700 140" width="700" height="140">
  <defs>
    <linearGradient id="homeBg" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" style="stop-color:#1a1200;stop-opacity:1"/>
      <stop offset="100%" style="stop-color:#0d1a0e;stop-opacity:1"/>
    </linearGradient>
    <linearGradient id="homeAccent" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" style="stop-color:#F59E0B;stop-opacity:1"/>
      <stop offset="100%" style="stop-color:#10B981;stop-opacity:1"/>
    </linearGradient>
  </defs>
  <rect width="700" height="140" fill="url(#homeBg)" rx="12"/>
  <text x="350" y="55" font-family="Arial, sans-serif" font-size="40" font-weight="700" fill="url(#homeAccent)" text-anchor="middle">pyLoan Wiki</text>
  <text x="350" y="88" font-family="Arial, sans-serif" font-size="15" fill="#C0B090" text-anchor="middle">Everything you need — no StackOverflow tab required</text>
  <rect x="100" y="104" width="500" height="4" rx="2" fill="url(#homeAccent)" opacity="0.7"/>
</svg>

</div>

---

Welcome to the **pyLoan** wiki. This is the complete documentation for a fully offline desktop EMI calculator built with Python, PyQt5, and Matplotlib.

If you're reading this, you either want to use pyLoan, contribute to it, or you accidentally ended up here from a Google search. All three are valid. Make yourself at home.

---

## 📚 Wiki Pages

| Page | What's in it |
|---|---|
| [Architecture](Architecture.md) | How the code is structured and why |
| [Installation](Installation.md) | How to get it running on your machine |
| [Usage](Usage.md) | How to actually use the calculator |
| [Privacy](Privacy.md) | What data pyLoan does (and doesn't) collect |
| [Troubleshooting](Troubleshooting.md) | When things go wrong (and they will) |
| [Roadmap](Roadmap.md) | What's coming next |

---

## 🔍 What is pyLoan?

**pyLoan** is a desktop Loan EMI calculator. You give it numbers, it tells you how much money you'll be giving your bank every month for the next 20 years. It also draws charts about it, because data is better visualised than imagined.

Key things to know upfront:

- **100% offline.** Nothing phones home. Not one byte leaves your machine.
- **Single Python file.** `pyLoan.py`. The whole app. No package structure to navigate, no `__init__.py` archaeology.
- **Two layers:** a pure calculation engine (testable without a display) and a PyQt5 GUI on top.
- **Python 3.8+** required. If you're on 2.7, the exit is that way →.

---

## 🚀 Quick Start

```bash
git clone https://github.com/Kaelith69/pyLoan.git
cd pyLoan
pip install PyQt5 matplotlib numpy
python pyLoan.py
```

That's it. The window opens. Fill in numbers. Click **Calculate EMI**. Your financial future is now a bar chart.

---

## 🤝 Contributing

Found a bug? See [CONTRIBUTING.md](../../CONTRIBUTING.md). We promise the contribution process won't be more painful than the loan itself.

---

## 📄 License

MIT. See [LICENSE](../../LICENSE). Free as in "free software" and also free as in "no one will charge you for this calculator."
