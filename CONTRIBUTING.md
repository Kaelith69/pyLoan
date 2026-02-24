# Contributing to pyLoan 🎉

First off — thanks for wanting to contribute! Whether you're fixing a bug, adding a feature, or just correcting a typo, you're appreciated. PRs are welcome. Hugs are optional but also welcome.

---

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [Branching Model](#branching-model)
- [Commit Style](#commit-style)
- [Submitting a PR](#submitting-a-pr)
- [What to Work On](#what-to-work-on)
- [What NOT to Do](#what-not-to-do)

---

## Code of Conduct

Be kind. Don't be weird. Treat others the way you'd want your code to be reviewed. That's it. We're all here because we like Python and hate calculating EMIs manually.

---

## Getting Started

1. **Fork the repository** — that little fork button up top, yes, click it
2. **Clone your fork:**
   ```bash
   git clone https://github.com/YOUR_USERNAME/pyLoan.git
   cd pyLoan
   ```
3. **Set up your environment:**
   ```bash
   python -m venv .venv
   source .venv/bin/activate   # Linux/macOS
   .venv\Scripts\activate      # Windows
   pip install PyQt5 matplotlib numpy
   ```
4. **Confirm it runs:**
   ```bash
   python pyLoan.py
   ```
   If a dark-themed window opens and doesn't immediately crash, you're good.

---

## Branching Model

We keep it simple. This is not a Fortune 500 company.

| Branch | Purpose |
|---|---|
| `main` | Stable, working code. Don't break this. |
| `feature/your-feature-name` | New features — branch off `main` |
| `fix/what-you-are-fixing` | Bug fixes — branch off `main` |
| `docs/what-you-updated` | Documentation only |

**Examples:**
```bash
git checkout -b feature/export-to-csv
git checkout -b fix/division-by-zero-tenure
git checkout -b docs/update-wiki-installation
```

Keep your branches focused. One thing per branch. Don't commit your entire life's work in one PR.

---

## Commit Style

Use [Conventional Commits](https://www.conventionalcommits.org/) because future-you will thank present-you.

```
<type>(<scope>): <short description>

[optional body]
```

**Types:**
- `feat` — new feature
- `fix` — bug fix
- `docs` — documentation changes only
- `refactor` — code change that neither fixes a bug nor adds a feature
- `test` — adding or updating tests
- `chore` — maintenance, dependency updates, etc.

**Good examples:**
```
feat(calc): add floating interest rate support
fix(ui): prevent crash when tenure field is empty
docs(readme): add installation troubleshooting section
refactor(calc): extract amortisation logic into helper function
```

**Bad examples:**
```
fixed stuff
update
asdfasdf
WIP commit 3
```

Please don't. 🙏

---

## Submitting a PR

1. Push your branch to your fork
2. Open a Pull Request against `main`
3. Fill in the PR template (or at least write a few sentences explaining what you did and why)
4. Wait for review — we try to be fast, but we're human

**PR checklist:**
- [ ] Code runs without errors
- [ ] Existing behaviour is unchanged (unless the PR intentionally changes it)
- [ ] New logic is reasonably readable
- [ ] Commit messages are sensible

If your PR is a work-in-progress, prefix the title with `[WIP]` so reviewers know not to merge it yet.

---

## What to Work On

Check the [Roadmap](wiki/Roadmap.md) for ideas. Open issues are also fair game. If you're about to tackle something big, open an issue first to discuss it so we don't duplicate effort.

Some things that would be great:
- Unit tests for the three calculation functions (they're pure functions, they're just begging to be tested)
- PDF/CSV export
- Amortisation schedule table view
- Multiple lump-sum payment support

---

## What NOT to Do

- Don't reformat the entire file for style reasons in the same PR as a feature/fix
- Don't add dependencies without a very good reason
- Don't remove existing functionality without discussing it first
- Don't commit secrets, credentials, or `.env` files (seriously, don't)
- Don't open a PR that just changes whitespace

---

Still here? You're a legend. Go build something cool. ⚡
