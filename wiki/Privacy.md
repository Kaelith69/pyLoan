# Privacy

Short version: **pyLoan doesn't collect anything. Ever. Full stop.**

Longer version follows, for the skeptics among us (a healthy instinct, honestly).

---

## What Data Does pyLoan Collect?

None.

Zero bytes.

Not a single keystroke, calculation result, or window resize event leaves your machine.

---

## Network Activity

pyLoan makes **zero network requests**. There is no:

- Analytics endpoint
- Crash reporter
- Auto-updater
- License check
- "Send anonymous usage stats" checkbox (which is never actually anonymous)
- Background sync
- Cloud storage

The application imports `sys`, `PyQt5`, `matplotlib`, and `numpy`. None of those make network calls during normal operation. You can verify this yourself with a network monitor if you enjoy that kind of thing.

---

## File System Access

pyLoan does **not read or write any files** during normal operation. Specifically:

- No log files
- No preferences or config files
- No cache files
- No temporary files written to disk
- No "recent calculations" stored anywhere

Your loan parameters exist only in RAM and disappear the moment you close the window. It's the most GDPR-compliant calculator in the world by virtue of storing nothing.

---

## What About Dependencies?

The three dependencies (PyQt5, matplotlib, numpy) are standard, widely-used libraries with their own privacy policies. pyLoan uses them purely for:

| Library | How It's Used |
|---|---|
| `PyQt5` | Rendering the GUI widgets locally |
| `matplotlib` | Drawing charts in memory, displaying them in the Qt canvas |
| `numpy` | Generating integer arrays for chart axes |

None of these usages involve sending data externally.

---

## Local Environment

When you run pyLoan, it has the same access rights as any Python process you run. It could theoretically read your files — but the code doesn't, and you can verify that by reading the 389 lines in `pyLoan.py`. It's short enough to audit over a coffee.

---

## Summary

| Question | Answer |
|---|---|
| Does it phone home? | No |
| Does it write files? | No |
| Does it log anything? | No |
| Can I trust it with real loan numbers? | Yes — your numbers never go anywhere |
| Is this GDPR compliant? | By default, yes — no data is processed externally |

---

*[← Back to Home](Home.md)*
