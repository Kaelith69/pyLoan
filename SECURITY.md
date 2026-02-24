# Security Policy

## Supported Versions

| Version | Supported |
|---|---|
| 1.1.x | ✅ Yes |
| 1.0.x | ⚠️ Best-effort (upgrade recommended) |
| < 1.0  | ❌ No |

---

## Reporting a Vulnerability

If you discover a security vulnerability in pyLoan, please **do not open a public GitHub issue**. Instead, report it privately so we can investigate and release a fix before any public disclosure.

### How to Report

**Via GitHub:** Open a [GitHub Security Advisory](https://github.com/Kaelith69/pyLoan/security/advisories/new) via the repository's **Security** tab → **Report a vulnerability**.

Please include:

1. **Description** — A clear description of the vulnerability and what it allows an attacker to do.
2. **Steps to reproduce** — Enough detail to reliably reproduce the issue.
3. **Impact** — Your assessment of severity (e.g., data exposure, code execution, denial of service).
4. **Affected version(s)** — Which version(s) you tested against.
5. **Suggested fix** (optional but appreciated) — If you have an idea of how to address it.

---

## What to Expect

| Step | Timeline |
|---|---|
| Acknowledgement of your report | Within **3 business days** |
| Initial assessment and severity triage | Within **7 days** |
| Fix or mitigation released | Depends on severity — critical issues targeted within **14 days** |
| Public disclosure (coordinated) | After fix is released and users have had time to update |

We follow **coordinated disclosure**: we will work with you to set a public disclosure date that gives users reasonable time to update, and we will credit you in the release notes if you wish.

---

## Scope

pyLoan is a **fully offline desktop application**. It:

- Does not connect to any network or API
- Does not store user data to disk
- Does not execute external processes or shell commands
- Does not load plugins or external scripts

Given this, the most relevant threat surfaces are:

- **Dependency vulnerabilities** in PyQt5, Matplotlib, or NumPy (report to the respective upstream projects; we will update our dependency recommendations accordingly)
- **Code injection via malformed input** (all user inputs are validated via Qt validators and Python `float()`/`int()` casting — but edge cases are worth reporting)
- **Denial-of-service via pathological inputs** (e.g., an input that causes the calculator to spin forever)

---

## Out of Scope

The following are **not** considered security vulnerabilities for this project:

- Issues in Python itself or the operating system
- Requests to add features
- Bugs that do not have a security impact (use the regular [issue tracker](https://github.com/Kaelith69/pyLoan/issues) for those)

---

*Thank you for helping keep pyLoan secure and trustworthy. Responsible disclosure is appreciated more than you know.*
