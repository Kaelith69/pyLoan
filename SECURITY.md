# Security Policy

## The Short Version

pyLoan is a local desktop calculator. It has no network access, no server, no database, and no authentication system. The attack surface is approximately the size of a Post-it note. But we still take security seriously, because you deserve that.

---

## Supported Versions

| Version | Supported |
|---|---|
| 1.1.x | ✅ Yes |
| 1.0.x | ⚠️ Best-effort |
| < 1.0 | ❌ No |

We only actively maintain the latest release. If you're on an older version, please upgrade before reporting.

---

## Reporting a Vulnerability

Found something sketchy? Don't post it publicly as a GitHub issue. That gives bad actors a free head start.

**Instead, please:**

1. **Email the maintainer directly** — open a GitHub issue with the title `[SECURITY] Private disclosure request` and we'll coordinate from there.
2. Include:
   - A description of the vulnerability
   - Steps to reproduce it
   - What you think the impact is
   - Your suggested fix, if you have one

We'll acknowledge receipt within **48 hours** and aim to resolve confirmed issues within **14 days**, depending on complexity.

If you want credit in the changelog, just say so — we're happy to call out responsible disclosures.

---

## What Counts as a Security Issue Here?

Realistic scope for a local desktop app:

- **Malicious input handling** — could a crafted input cause unintended code execution or crash in a way that leaks data?
- **Dependency vulnerabilities** — if a known CVE in PyQt5, matplotlib, or NumPy affects pyLoan's usage pattern
- **Code execution via file paths** — if we ever add file I/O, any path traversal or injection issue

Not in scope:
- "The app crashes if I type letters in a number field" — that's a bug, not a security issue (but feel free to report it as a bug anyway)
- The fact that your loan has a lot of interest — that's between you and your bank

---

## Third-Party Dependencies

pyLoan depends on:

| Package | Purpose |
|---|---|
| `PyQt5` | GUI framework |
| `matplotlib` | Chart rendering |
| `numpy` | Numeric array operations for chart data |

Monitor these for CVEs if you're deploying pyLoan in a sensitive environment. We recommend keeping dependencies up to date.

---

Thanks for helping keep pyLoan safe. You're the real MVP. 🛡️
