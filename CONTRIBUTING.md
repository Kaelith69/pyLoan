# Contributing to pyLoan

First off — welcome, and thank you for considering a contribution. You've presumably stared at this repo long enough that you want to make it better, which means you're already better than most.

---

## 🐛 Found a Bug?

Congratulations. You are now officially part of the development team. Please file an [issue](https://github.com/Kaelith69/pyLoan/issues) and include:

- **What you did** (be honest — we've all typed `-1` into a validator at some point)
- **What you expected to happen**
- **What actually happened** (screenshots welcome, especially if the window turned into a black hole)
- **Your OS, Python version, and PyQt5 version**

---

## 💡 Want to Add a Feature?

Open an issue first and describe what you want to build. This saves you from spending a weekend writing code only to hear "we actually had this on a branch already." Not fun. Ask us first.

---

## 🔧 How to Contribute Code

1. **Fork** the repository and clone your fork locally.

2. **Create a branch** with a descriptive name:
   ```bash
   git checkout -b feature/pdf-export
   # or
   git checkout -b fix/zero-division-rate
   ```

3. **Make your changes.** Keep them focused — one feature or fix per PR. A PR that rewrites the entire UI *and* adds currency support *and* fixes a typo will be politely declined and used as a cautionary tale.

4. **Test your changes.** The calculation functions (`calculate_emi`, `calculate_outstanding_principal`, `calculate_new_emi_after_lump`) are pure Python — you can test them directly with `assert` statements or your test framework of choice without spinning up a Qt application.

5. **Follow PEP 8.** You don't have to be a formatting robot, but at least run `python -m py_compile pyLoan.py` to confirm the file parses. Extra credit for `flake8`.

6. **Open a Pull Request** against `main`. Fill out the description — explain *why*, not just *what*. Future maintainers will thank you.

---

## 📐 Code Style

- **Snake_case** for everything Python-related. No camelCase sneaking in from a JavaScript past.
- **Docstrings** on new functions, please. Even a one-liner is better than nothing.
- **No magic numbers** buried in logic. If `8.5` means something specific, name it.
- **Keep the calculation layer pure.** The three `calculate_*` functions must not import or reference anything Qt-related. Ever.

---

## 🚫 What We Won't Merge

- Code that breaks existing functionality with no explanation
- Dependencies that require a C compiler, a Docker daemon, or a prayer
- Features that require an internet connection (pyLoan is proudly offline-first)
- Anything that phones home, logs user data, or adds analytics. This is a loan calculator, not a SaaS startup.

---

## 🤝 Code of Conduct

Be kind. Be constructive. Assume good faith. If someone's PR isn't great, explain *why* instead of just pasting the skull emoji. We're all here to make something better.

---

*Thanks again for contributing. Your future self (and your mortgage) will appreciate it.*
