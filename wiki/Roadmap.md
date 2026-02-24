# Roadmap

These are things that might happen. No ETAs. No sprint planning. No Jira tickets. Just ideas in priority-ish order.

---

## Status Legend

| Symbol | Meaning |
|---|---|
| ✅ | Done |
| 🔨 | In progress / being considered |
| 💡 | Good idea, not started |
| 🌀 | Wild idea, probably won't happen, but who knows |

---

## Core Improvements

### ✅ v1.1.0 — Bug fixes and edge-case handling
0% interest rate, negative rate guard, zero-tenure guard, float month indexing. See [CHANGELOG](../CHANGELOG.md).

### 💡 Unit tests for calculation functions
The three pure functions (`calculate_emi`, `calculate_outstanding_principal`, `calculate_new_emi_after_lump`) are perfectly shaped for unit tests. They take numbers, return numbers, have no side effects. This would be the easiest test suite in the world to write.

### 💡 Amortisation schedule table
A full month-by-month breakdown: payment number, principal component, interest component, cumulative interest, outstanding balance. Optionally scrollable in the app, optionally exportable.

### 💡 Multiple lump-sum payments
Right now you can simulate one lump-sum prepayment. Real life often has more than one "I found extra money" moment. Supporting a list of prepayments (amount + year) would make the simulation significantly more useful.

---

## Export & Sharing

### 💡 Export to CSV
Save the amortisation schedule to a CSV file. Spreadsheet people would love this. Banks would probably hate it.

### 💡 Export to PDF
Generate a clean PDF summary of the loan calculation — useful for personal records or showing your bank their own math with your own numbers.

---

## Calculation Enhancements

### 💡 Floating / adjustable interest rate
Many loans (especially home loans) have rates that change over time. Simulating a rate change at year N would be genuinely useful for long-term planning.

### 💡 Comparison mode
Side-by-side comparison of two loan scenarios — different rates, different tenures, different lump sums. Useful when choosing between two bank offers and you want to see the numbers next to each other.

### 💡 Currency selector
Currently the app hardcodes `₹` (Indian Rupee). A simple currency switcher (symbol only, not conversion) would make it more useful internationally.

---

## UI / UX

### 💡 Enter key triggers calculation
Pressing Enter in any input field should be equivalent to clicking "Calculate EMI". Currently only the button works.

### 💡 Input persistence
Optionally save the last-used values to a config file so you don't retype them every time the app opens.

### 💡 Result copy to clipboard
A small "Copy" button next to the results panel so you can paste the output somewhere without manually selecting text.

---

## Wild Ideas

### 🌀 Plugin system
Let the app load custom calculation modules. Overly complex for this project. Probably not happening.

### 🌀 Web version
Port to a browser-based interface. Would require replacing PyQt5 with something else entirely. Loses the "single Python file" simplicity. Maybe, one day.

### 🌀 Loan comparison against historical mortgage data
Show how your loan terms compare to average rates. Requires network access, which goes against the privacy-first design. Probably won't happen.

---

## Contributing to the Roadmap

Got an idea not on this list? [Open an issue](https://github.com/Kaelith69/pyLoan/issues) and describe it. Feature requests are welcome. Wild ideas are fun. Just be specific about what you'd want it to do.

If you want to implement something from this list — even better. Check [CONTRIBUTING.md](../CONTRIBUTING.md) and go for it.

---

*[← Back to Home](Home.md)*
