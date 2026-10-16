# Sample Scenarios — Pick One for Training

Each scenario below is a complete, ready-to-demo example: folder, starter files, one connector, one schedule. Pick whichever matches your audience best, or offer two and let the room split.

All three follow the same minimal pattern from the training script — three flat files, no subfolders unless the agent produces real output to keep (noted per-scenario where that applies).

---

## Scenario 1 — Personal Assistant (general-purpose, safest first demo)

**What it does:** each morning, reads your calendar and email, tells you what matters today.

**Folder:** `MorningBriefAgent/`

```
MorningBriefAgent/
├── CLAUDE.md
├── memory.md
└── progress.md
```

**`CLAUDE.md`**
```markdown
# Morning Brief Agent

You help me start the day. Every morning you check my calendar and
inbox and give me a short summary — nothing I have to click through.

Rules:
- Keep the summary under 10 lines.
- Flag anything time-sensitive (meetings in the next 2 hours, replies
  someone is waiting on) at the top.
- Never send a reply or accept/decline a meeting without asking me first.
```

**`memory.md`**
```markdown
# About Me
- Timezone: Europe/Dublin
- Work hours: 9am–6pm, Mon–Fri
- I don't want weekend calendar items included unless marked "urgent"
- Recurring: Monday 10am team standup, Friday 4pm 1:1 with my manager
```

**`progress.md`** (overwritten each run — current state only)
```markdown
# Current State
Last brief sent: this morning, 8:02am.
Nothing flagged as urgent today.

# Next Step
Tomorrow's brief should also mention the client call moved to 2pm
(confirmed by email yesterday) — don't let it get buried once it's
past, remove this note after tomorrow's run.
```

**Connector:** Google Calendar + Gmail (read-only is enough for the demo)

**Schedule:** "Every weekday at 8am, check my calendar and inbox, and give me a short summary of what matters today. Flag anything time-sensitive first."

---

## Scenario 2 — Email Agent

**What it does:** triages inbox, drafts replies to routine messages, never sends without approval.

**Folder:** `EmailAgent/`

```
EmailAgent/
├── CLAUDE.md
├── memory.md
└── progress.md
```

**`CLAUDE.md`**
```markdown
# Email Agent

You help me manage email. You read my inbox, sort what's actually
important from what isn't, and draft replies to routine messages.

Rules:
- NEVER send an email. Draft it and show me — I send it myself.
- Anything from my manager or a client goes to the top, always.
- Newsletters and automated notifications: just mark as read, don't
  draft anything for those.
```

**`memory.md`**
```markdown
# About Me / My Email
- My manager's email: jordan@company.com
- Key clients: Acme Co (billing@acme.com), Riverside LLC
- Tone for client replies: friendly but professional, no exclamation points
- I'm currently waiting on a reply from Acme about the Q3 invoice
  (sent Oct 10) — flag if they respond
```

**`progress.md`**
```markdown
# Current State
Inbox triaged as of 9:15am. 2 drafts waiting for my review (client
reply to Riverside, RSVP to Friday's event).

# Next Step
Still waiting on Acme's Q3 invoice reply (see memory.md) — check
every run, remove this once they respond.
```

**Connector:** Gmail (or Outlook, if that's what the room uses)

**Schedule:** "Three times a day (9am, 1pm, 5pm), check my inbox, flag anything from my manager or key clients, and draft replies to routine messages for my review. Never send anything yourself."

> Note for the trainer: this is the scenario most likely to prompt the "wait, can it accidentally send something?" question. Lean into the "never send, only draft" rule in `CLAUDE.md` — it's a good live example of a hard rule earning its place in that file.

---

## Scenario 3 — Personal Finance Advisor

**What it does:** weekly check on spending against a budget, flags anything unusual, no automated transactions.

**Folder:** `FinanceAdvisor/`

```
FinanceAdvisor/
├── CLAUDE.md
├── memory.md
├── progress.md
└── exports/        ← only add this once there's a real weekly report to keep
```

**`CLAUDE.md`**
```markdown
# Finance Advisor

You help me track spending against my monthly budget. Once a week
you summarize where I stand and flag anything that looks off.

Rules:
- NEVER move money, pay a bill, or take any action on an account —
  read and report only.
- Round all numbers, don't show exact cents.
- If something looks like a duplicate charge or a sudden spike in a
  category, say so clearly at the top.
```

**`memory.md`**
```markdown
# My Budget
- Monthly budget: Rent 1400, Groceries 400, Dining out 200, Fun 150
- Paydays: 1st and 15th
- I save whatever's left over at the end of the month — no fixed
  savings target yet
- Flag anything over 50 in a single "Fun" transaction
```

**`progress.md`**
```markdown
# Current State
As of this week: on track for Groceries and Rent, 30 over on Dining
out with 10 days left in the month.

# Next Step
Keep an eye on Dining out — if it goes another 50 over, call it out
specifically next week instead of just the usual summary.
```

**Connector:** whatever your bank/budgeting app offers as a read-only connector (demo with a sandbox or sample account if the real one isn't safe to show live)

**Schedule:** "Every Sunday evening, check my spending against my budget categories and give me a short summary. Flag anything unusual."

> Note for the trainer: this is the one scenario where the `exports/` folder earns a mention in Part 7 of the script — it's the concrete example of "add structure only once there's something to put in it." A weekly PDF or spreadsheet export is a good reason; nothing else in this scenario needs it.

---

## Picking a scenario for your room

| If your audience is... | Use |
|---|---|
| Mixed / unsure | Scenario 1 (Personal Assistant) — lowest stakes, broadest appeal |
| Office workers drowning in email | Scenario 2 (Email Agent) — most relatable pain point |
| Audience that reacts to "money" demos | Scenario 3 (Finance Advisor) — but budget extra time for the "is this safe?" questions |
