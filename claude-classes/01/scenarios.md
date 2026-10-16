# Scenarios — Six Agents You Can Build Today

Pick **one** to demo. Let attendees pick their own.

Each scenario lists: what it does (and deliberately *doesn't*), which connectors at which level (👀 look / ✍️ draft / 🖐️ act — see the script, Part 5), the folder, the skills, the schedules, the opening interview prompt, and what a good result looks like.

The first three have **full, copy-paste-ready starter kits** in [`starter-kits/`](starter-kits/).

## Which one should I demo?

| Scenario | Wow factor | Risk if it misbehaves | Needs a connector? | Best for a room of… |
|---|---|---|---|---|
| 1. Morning Brief | ⭐⭐⭐ | Very low — read only | Calendar + Gmail | Anyone. **Default choice.** |
| 2. Email Helper | ⭐⭐⭐ | Low — drafts only | Gmail | Office workers |
| 3. Money Check-in | ⭐⭐ | Very low — no account access at all | None required | Privacy-conscious people; shows off *Local* best |
| 4. Meeting Prep & Follow-up | ⭐⭐⭐ | Low | Calendar + Drive/Notion | Managers, consultants, sales |
| 5. Learning Buddy | ⭐⭐ | None | None (web) | Students, career-changers |
| 6. Household Admin | ⭐⭐ | Low | Calendar + Gmail | Parents, anyone with a household |

---

## 1. Morning Brief — the personal assistant 🌅

**One line:** every weekday morning, a 10-line summary of what matters today, before you've opened your inbox.

**Does:** reads today's calendar and recent email, cross-references with what it knows about you, flags anything time-sensitive, remembers what it flagged yesterday.
**Doesn't:** reply, accept, decline, archive, or move anything. Ever.

**Connectors:** Google Calendar 👀 · Gmail 👀

**Folder:** → [`starter-kits/morning-brief/`](starter-kits/morning-brief/)
```
MorningBrief/
├── CLAUDE.md                      job description + rules
├── memory.md                      you, your week, your people
├── progress.md                    yesterday's flags → today
├── briefs/                        (created by the agent) one file per day
└── .claude/skills/morning-brief/
    └── SKILL.md                   the recipe for building a brief
```

**Schedules:**

| When | Instruction (short form — full version in the kit) |
|---|---|
| Weekdays 08:00 | Build today's brief using the morning-brief skill; save to `briefs/`; update progress. |
| Friday 16:00 | Look back at this week's briefs; list anything I flagged but never dealt with. |
| Sunday 19:00 | Preview next week: busiest day, conflicts, anything to prepare. |

**Opening interview prompt:**
```
Be my morning brief assistant. Interview me (max 8 questions, one at
a time) about my work hours, timezone, recurring meetings, the people
whose emails always matter, and what I want to never be bothered
with. Then create CLAUDE.md, memory.md and progress.md.
```

**What good looks like:**
```
☀️ Tuesday 14 Oct

⏰ TIME-SENSITIVE
• 10:00 standup — you're presenting Q3 numbers (flagged Fri)
• Priya replied to the contract thread at 23:40 — she's waiting on you

📅 TODAY: 4 meetings, free block 13:00–15:00
📬 Worth reading: 3 · Ignorable: 41 newsletters/notifications
↩️ From yesterday: client call moved to 14:00 — confirmed ✅
```

**Teaching moment:** the "↩️ From yesterday" line. That's `progress.md` working. Point at it.

---

## 2. Email Helper ✉️

**One line:** sorts your inbox three times a day and has polite drafts waiting for the routine stuff. You hit send.

**Does:** triages into *needs you / FYI / ignore*, drafts replies in your tone, tracks threads you're waiting on.
**Doesn't:** send. Deletes nothing. Unsubscribes from nothing (unless you ask, in the moment).

**Connectors:** Gmail ✍️ (draft level — it can create drafts, you send)

**Folder:** → [`starter-kits/email-agent/`](starter-kits/email-agent/)
```
EmailHelper/
├── CLAUDE.md
├── memory.md                      VIPs, tone, waiting-on list
├── progress.md
└── .claude/skills/
    ├── inbox-triage/SKILL.md      how to sort
    └── draft-reply/SKILL.md       how to write in my voice
```

**Schedules:**

| When | Instruction |
|---|---|
| Weekdays 09:00, 13:00, 17:00 | Triage new mail since the last run; draft replies for routine items; list what needs me. |
| Monday 09:00 | Anything I'm "waiting on" for more than 5 days? Draft a polite nudge for each. |

**Opening interview prompt:**
```
Be my email assistant. Interview me (max 8 questions) about who my
VIPs are, how I like to sound in replies, what's always safe to
ignore, and anything I'm currently waiting to hear back about.
Then create CLAUDE.md, memory.md and progress.md. You must never
send email — only draft.
```

**Teaching moment:** the hard rule *"never send — only draft"* in `CLAUDE.md`. Ask the room: "what's the worst thing that could happen if this rule weren't there?" They'll tell you. That's why rules live in `CLAUDE.md`.

**Pro move to show:** the `draft-reply` skill has 2–3 **examples of your real past emails** pasted in. Drafts go from "generic AI" to "sounds like me" instantly. Examples beat descriptions.

---

## 3. Money Check-in 💶 — the personal finance advisor

**One line:** once a week, tells you how you're doing against your budget and what looks odd.

**Does:** reads bank statement exports you drop into a folder, categorises spending, compares to your budget, spots duplicates and creeping subscriptions.
**Doesn't:** touch any bank account. There's no bank connector at all — **this is the perfect showcase for Local**: your statements never leave your laptop.

**Connectors:** none required. (Optional: Google Sheets 👀 if your budget lives in a sheet.)

**Folder:** → [`starter-kits/finance-advisor/`](starter-kits/finance-advisor/)
```
MoneyCheck/
├── CLAUDE.md
├── memory.md                      budget, paydays, known subscriptions
├── progress.md                    this month so far
├── statements/                    ← YOU drop your bank CSV export here
├── exports/                       ← it writes weekly reports here
└── .claude/skills/weekly-money-check/SKILL.md
```

**Schedules:**

| When | Instruction |
|---|---|
| Sunday 19:00 | Run the weekly money check on any new file in `statements/`; save report to `exports/`. |
| 1st of month | Close last month: totals by category vs budget, biggest surprise, one suggestion. |
| 1st of month | List every recurring charge; flag any new ones or price increases. |

**The one manual step:** download your statement as CSV from your bank and drop it in `statements/`. Say this plainly — it's a feature, not a limitation: *"it only ever sees what you hand it."*

**What good looks like:**
```
💶 Week of 6–12 Oct

On track: Rent ✅  Groceries ✅ (€212 / €400)
Watch:    Dining out €165 / €200 — 19 days left in the month
⚠️ Spotify charged twice on 8 Oct (€10.99 × 2) — likely duplicate
🆕 New recurring charge: "Calm.com" €69.99/yr — did you mean to sign up?
```

**Teaching moment:** the 🆕 line. Nobody notices a new annual subscription; this agent does, every month, forever. Small, real money.

---

## 4. Meeting Prep & Follow-up 🗓️

**One line:** before each important meeting, a one-page brief; after it, a follow-up list.

**Does:** the evening before, looks at tomorrow's external meetings, pulls related emails/docs, writes a prep note per meeting; after the meeting (you paste or drop your notes in), extracts action items and drafts the follow-up email.
**Doesn't:** join meetings or record anything.

**Connectors:** Google Calendar 👀 · Gmail 👀 · Google Drive or Notion 👀

**Folder:**
```
MeetingPrep/
├── CLAUDE.md
├── memory.md                      clients, projects, who's who
├── progress.md                    open action items across meetings
├── meetings/                      one file per meeting: prep + notes + actions
└── .claude/skills/
    ├── meeting-prep/SKILL.md
    └── follow-up/SKILL.md
```

**Schedules:**

| When | Instruction |
|---|---|
| Weekdays 18:00 | For each external meeting tomorrow: who, why, last contact, open items, 3 smart questions. Save to `meetings/`. |
| Friday 15:00 | List every action item from this week's meetings that's still open, by owner. |

**Teaching moment:** `progress.md` here holds **open action items across all meetings** — shows how the "current state" sticky note scales beyond a single task.

---

## 5. Learning Buddy 📚

**One line:** helps you learn one topic steadily, a little every day, and remembers where you are.

**Does:** keeps a learning plan, gives a short daily lesson or reading, quizzes you, tracks what you've got and what keeps tripping you up.
**Doesn't:** do your homework for you (put that in `CLAUDE.md` if it's for a student!).

**Connectors:** none (uses web search). Optional: Notion/Drive 👀 for your own notes.

**Folder:**
```
LearnSpanish/                      (or LearnPython, LearnInvesting…)
├── CLAUDE.md                      teaching style, level, rules
├── memory.md                      what I know, what I keep getting wrong
├── progress.md                    where we are in the plan, today's lesson
├── plan.md                        the syllabus it built with you
└── lessons/
```

**Schedules:**

| When | Instruction |
|---|---|
| Daily 07:30 | Today's 10-minute lesson based on progress.md; end with 3 quiz questions. |
| Sunday | Review the week; update memory.md with what's solid and what's shaky; adjust plan.md. |

**Teaching moment:** `memory.md` here is "what I keep getting wrong." This is the clearest example in the whole set of *why memory matters* — a tutor who remembers your weak spots.

---

## 6. Household Admin 🏠

**One line:** keeps track of the boring things that bite when forgotten: renewals, bills, school dates, appointments.

**Does:** maintains a list of every renewal and due date, watches email for bills and school notices, warns you 2 weeks ahead.
**Doesn't:** pay anything or book anything.

**Connectors:** Gmail 👀 · Google Calendar ✍️ (it can *suggest* calendar entries)

**Folder:**
```
HomeAdmin/
├── CLAUDE.md
├── memory.md                      household members, providers, account renewal dates
├── progress.md                    what's due in the next 30 days
└── documents/                     policies, warranties you drop in
```

**Schedules:**

| When | Instruction |
|---|---|
| Monday 08:00 | What's due in the next 14 days? Anything new from school, utilities or insurers in the inbox? |
| 1st of month | Scan `documents/` and email for renewal dates; update memory.md; flag anything within 60 days. |

**Teaching moment:** drop a car-insurance PDF into `documents/` live and ask *"when does this renew and what's the excess?"* — instant, tangible, and shows off reading local files.

---

## More ideas for the Q&A

- **Job search coach** — tracks applications, tailors CVs per posting, preps interviews, nudges follow-ups.
- **Health & fitness log** — you message what you ate/did; weekly trends against your goals.
- **Content creator assistant** — keeps your content calendar, drafts posts in your voice, tracks what performed.
- **Small-business back office** — invoices due, overdue payments, weekly cash snapshot from exported CSVs.
- **Travel planner** — one folder per trip; itinerary, bookings from email, packing list, day-by-day plan.

Every one of them is the same four pieces: desk, notebook, hands, alarm clock.
