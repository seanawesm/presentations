# Rolling Out a Personal Agent in 30 Minutes — Trainer Script

**Audience:** non-technical. Nobody in the room should need to know what "MCP" or "context window" means.
**Goal by the end:** everyone leaves with one working personal agent that (a) has a home folder, (b) is connected to one real tool, and (c) can run a task on a schedule without them lifting a finger.
**Format:** you talk + demo on screen, they follow along on their own laptop at the same time.

> ⚠️ Before you present: Claude Desktop's exact menu wording (Connectors, Schedules/Routines, Settings) can change between versions. Walk through Parts 3–5 on your own machine the morning of the session and swap in whatever the buttons actually say. Don't read this script's click-paths verbatim without checking first.

---

## What attendees need before the session starts

Put this on the invite, not in the first 5 minutes of the room:

- Claude Desktop installed and signed in
- One account they're comfortable connecting for the demo (their own Gmail or Google Calendar is the easiest — avoid anything sensitive for a first try)
- 30 uninterrupted minutes

---

## Timing overview

| Part | Topic | Time |
|---|---|---|
| 0 | Framing: what is a "personal agent"? | 2 min |
| 1 | Open Claude Desktop | 2 min |
| 2 | Create the agent's home folder | 5 min |
| 3 | Local vs. Cloud — and why it matters | 5 min |
| 4 | Connect one real tool | 5 min |
| 5 | Make it run on a schedule | 5 min |
| 6 | Bonus: make the schedule "remember" | 5 min |
| 7 | Three files that make it smart | 3 min |
| — | Wrap-up & questions | 3 min |

Total: ~35 min including wrap-up — trim Part 6 first if you're short on time, it's explicitly the bonus round.

---

## Part 0 — Framing (2 min)

**Say:**
"Think of this less like 'installing software' and more like hiring a very literal personal assistant. It doesn't know anything about you on day one. Everything it knows, it knows because you wrote it down somewhere it can read, or because you let it look at one of your accounts. Today we're going to give it a desk (a folder), a notebook (a couple of text files), and one task it does for you automatically."

Don't define "AI agent" abstractly — just point at what you're about to build.

---

## Part 1 — Open Claude Desktop (2 min)

**Do:** open the app, point out the chat window and the sidebar.

**Say:**
"This is the same Claude you may have used in a browser, but it runs on your own computer and can be given access to files and folders on your machine. That local access is what today is really about."

---

## Part 2 — Create the agent's home folder (5 min)

**Do:** on your desktop or in Documents, create a plain folder. Name it after what the agent will do, not "Claude" — e.g. `MorningBriefAgent`, not `ClaudeStuff`.

**Say:**
"This folder is the agent's home base. Nothing magic about it yet — it's just a folder. In a few minutes we'll drop a couple of plain text files in here, and that's what turns it from 'a chat window' into 'something that remembers you between conversations.'"

**Have attendees do the same**, naming their folder after whichever scenario they're building (see the Scenarios doc) — e.g. `EmailAgent`, `FinanceAdvisor`.

---

## Part 3 — Local vs. Cloud, and why it matters (5 min)

This is the part people skip past and then get confused by later. Don't skip it.

**Say, in plain terms:**

- **Local** means Claude Desktop, running on *your* computer, looking at *your* folder. It only works while your computer is on and the app is open. In exchange, it can read and write real files on your machine, and nothing leaves your computer unless you explicitly connect a tool.
- **Cloud** means a version of the agent runs on Anthropic's servers instead of your laptop. It works even when your computer is off or asleep — which is the whole point of a *schedule* (Part 5). The tradeoff: it can't casually browse your local hard drive like the local version can; it only sees what you've explicitly connected it to (your email, your calendar, a shared doc, etc).

**The rule of thumb to give them:**
> "If it's something you want to sit and work on *with* the agent — writing, organizing files, thinking out loud — do it locally. If it's something that should just *happen* on its own every morning whether you're at your desk or not, that's a cloud schedule."

**Demo:** show the same folder/workspace available to both the local app and a cloud schedule, so they see it's the *same* agent, just two different ways of running it — not two separate products.

---

## Part 4 — Connect one real tool (5 min)

**Do:** open Connectors (or whatever your version calls integrations), add exactly **one** — Gmail or Google Calendar is the friendliest first demo.

**Say:**
"A connector is a hookup to one of your real accounts — email, calendar, a notes app, whatever. Without one, the agent only knows what's in its folder. With one, it can actually look things up or take action for you. Start with one. You can always add more later — most people regret adding five connectors on day one and then not knowing which one broke."

**Have attendees connect the one matching their scenario.**

---

## Part 5 — Make it run on a schedule (5 min)

**Do:** create a schedule/routine: a plain-language instruction plus how often to run it (e.g. "every weekday at 8am, check my calendar and email, and summarize what matters today").

**Say:**
"This is the cloud half from Part 3 in action. You're not writing code — you're writing one sentence describing what you want done and how often. The agent runs that sentence on Anthropic's servers on the schedule you set, using whatever connector you gave it."

**Have attendees write their own one-line schedule** for their scenario (see Scenarios doc for starting points).

---

## Part 6 — Bonus: make the schedule "remember" (5 min)

Only do this part if Parts 1–5 landed and there's time left.

**Say:**
"Right now, every time the schedule runs, it's a little bit like groundhog day — it does the task but doesn't necessarily remember what it told you yesterday. If you point the schedule at the *same folder* you created in Part 2 — the one with its notes in it — it can read what happened last time before it acts this time. That's the difference between 'a task that repeats' and 'an assistant that's actually tracking something over weeks.'"

**Do:** show binding the schedule to the workspace folder from Part 2, so each run can read/update the files in it.

This is the bridge into Part 7 — the files are *what* it remembers with.

---

## Part 7 — Three files that make it smart (3 min)

**Say:**
"You don't need a filing system or a folder structure — three plain text files, sitting right in the folder, cover almost everyone's first agent. No subfolders yet; add one later only if the agent starts producing real files you need to keep, like an `exports/` folder — don't build structure before there's something to put in it."

| File | What goes in it | Analogy |
|---|---|---|
| `CLAUDE.md` | Short, *stable* instructions only — who it's helping, tone, hard rules ("never send an email without showing me first") | The job description |
| `memory.md` | Durable facts that can change over time — your timezone, recurring commitments, preferences, decisions, who's who | Its notebook |
| `progress.md` | Where things stand *right now*, and what to do next — nothing else | A sticky note, not a diary |

**Say the two mistakes almost everyone makes** — this is the single most useful thing in this whole session:

> **Mistake 1: letting `progress.md` grow into a log.**
> It's tempting to add a new entry every session and never delete the old ones. Don't. `progress.md` should be *overwritten* each time: "here's where things stand, here's what's next" — not a history. A file with fifty sessions of narrative in it means the agent has to wade through noise to find today's one fact, and it will eventually miss it.
>
> **Mistake 2: turning `CLAUDE.md` into a dumping ground.**
> Every one-off fact — "the client's name is X," "we decided to use Y" — gets pasted into `CLAUDE.md` because it's the file people know about, until it's 500 lines and the agent stops reading all of it. The test: if it's a fact that might change later, it belongs in `memory.md`. `CLAUDE.md` should stay short enough to reread in full, every single time.

**Say the one rule that prevents most of what's left:**
> "Update `memory.md`, don't duplicate it. If it says your meeting is Tuesdays and it changes to Wednesdays, edit that line — don't just add a new one and leave the old one in there confusing it."

See the Tips doc and Scenarios doc for filled-in examples per use case.

---

## Wrap-up & questions (3 min)

**Say:**
"You now have: a folder, one connected tool, one scheduled task, and three files it uses to stay consistent over time. That's the whole pattern — every more advanced thing you build later is just more of the same four pieces."

Point them at the Scenarios doc to pick their own project after the session, and the Tips doc for when something goes wrong.
