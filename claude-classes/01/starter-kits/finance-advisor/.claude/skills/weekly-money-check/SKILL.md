---
name: weekly-money-check
description: Reviews bank statement CSVs in statements/ against my budget and writes a short weekly report. Use for money check-ins, "how am I doing this month", or when the weekly money schedule runs.
---

# Weekly money check

1. **Find new data:** read any statement file in `statements/` that
   covers dates after the "last processed" date in progress.md.
   If there's nothing new, say so in one line and stop.
2. **Categorise** each transaction using "How my bank labels things"
   in memory.md. If you can't tell, put it under "Unsure" — don't guess.
3. **Compare** month-to-date totals with the budget in memory.md,
   accounting for how far through the month we are.
4. **Look for surprises:**
   - the same amount to the same merchant twice within 3 days → possible duplicate
   - a recurring charge not in "Known subscriptions" → new subscription
   - a known subscription that changed price
   - any single transaction more than 2× the usual for its category
5. **Write the report** in this shape, under 10 lines:
   ```
   💶 Week of [dates]

   On track: [categories ✅ with spent / budget]
   Watch:    [category spent / budget — days left in month]
   ⚠️ [possible duplicate or unusual charge]
   🆕 [new recurring charge — did you mean to sign up?]
   ❓ Unsure: [n] transactions — tell me what they are and I'll remember
   ```
6. **Save** to `exports/money-check-YYYY-MM-DD.md` and show it.
7. **Replace progress.md** with: last processed date, month-to-date
   totals per category, and what to watch next week.
