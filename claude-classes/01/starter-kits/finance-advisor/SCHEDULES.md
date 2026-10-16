# Schedules for this agent

Copy an instruction into a scheduled task. **Run it once by hand first.**

> The one manual step: download your bank statement as **CSV** and drop
> it into `statements/`. The agent never touches your bank — it only
> sees what you hand it. That's the point.

## Weekly check-in — Sunday 19:00
```
Run the weekly-money-check skill on any new file in statements/.
Save the report to exports/ and show it to me.
Never edit or delete anything in statements/.
Replace progress.md with the updated month-to-date picture.
```

## Month close — 1st of each month, 09:00
```
Close out last month: total spent per category vs budget, the biggest
surprise, and one practical suggestion for this month. Save it to
exports/month-YYYY-MM.md. Then reset progress.md for the new month.
```

## Subscription audit — 1st of each month, 09:15
```
List every recurring charge in the last 3 months of statements.
Mark each as known (in memory.md), new, or changed price.
For anything new or changed, ask me whether to keep it on the list.
```
