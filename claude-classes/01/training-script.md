# Trainer Script — Your First Personal Agent in 30 Minutes

**Audience:** non-technical. Nobody should need to know what "MCP," "context window," or "terminal" means — and you never say those words.
**Format:** you demo on screen, they follow on their own laptop, in lockstep.
**Outcome:** each attendee leaves with one agent that (1) has a home folder, (2) knows who they are, (3) is connected to one real account, and (4) does one job on a schedule.

---

> ### ⚠️ Verify before you present
> Claude Desktop changes often. The morning of the class, click through these on your own machine and write the *actual* button names into your notes:
> 1. Where you start a **Claude Code** session in the Desktop app, and where you pick **Local** vs **Cloud**.
> 2. Where you choose the **folder** for a local session.
> 3. Where **Connectors** are added (Settings → Connectors on most versions), and that the one you'll demo shows up inside a Claude Code session.
> 4. Where **scheduled tasks** live for local sessions, and how **routines** are created for cloud (the `/schedule` command or the web).
> 5. That a local scheduled task actually fires while the app is open — run one with a 2-minute schedule.
> 6. What the **permission prompt** looks like the first time Claude wants to edit a file, so you can warn the room before it appears.

---

## Pre-work (send with the invite)

Ask attendees to arrive with:

- [ ] Claude Desktop installed, updated, and signed in on a paid plan that includes Claude Code
- [ ] Google (or Microsoft) account they're comfortable connecting — **a personal one, not a work account with admin restrictions** (work accounts are the #1 cause of connectors failing to authorize in the room)
- [ ] A rough idea which agent they want: morning brief, email helper, or money check-in (link `scenarios.md`)
- [ ] Laptop charged — scheduled tasks on a laptop stop when it sleeps

## Your Plan B

Things that will go wrong in a room of 20 non-technical laptops, and what you do:

| If… | Then… |
|---|---|
| Someone's connector won't authorize | Pair them with a neighbour for that step, keep going. Their agent still works with just the folder and files. |
| The Wi-Fi is slow | Skip live connector auth on your machine; show your pre-connected fallback agent instead. |
| Someone falls behind | Every checkpoint below has a "catch-up" line. Don't stop the room for one person — the starter kits let them catch up afterwards. |
| You're running out of time | Cut Part 6 (bonus) entirely. Part 5 is the last part everyone must finish. |

---

## Run of show

| # | Part | Minutes | Running total |
|---|---|---|---|
| 0 | The four pieces (framing) | 3 | 3 |
| 1 | Open Claude Desktop, start a Claude Code session | 2 | 5 |
| 2 | Give it a desk: the workspace folder | 3 | 8 |
| 3 | Local or Cloud? | 4 | 12 |
| 4 | Give it a notebook: the three files + the interview | 6 | 18 |
| 5 | Give it hands: one connector | 4 | 22 |
| 6 | Give it an alarm clock: a schedule | 5 | 27 |
| 7 | Bonus: make every run remember (binding) | 4 | 31 |
| 8 | Wrap-up: your first week | 2 | 33 |

You'll notice this reorders your original outline slightly: **the files come before the connector**. That's deliberate — the "interview" in Part 4 is the moment the room goes *"oh, it actually knows me"*, and it works without any connector, so nobody gets stuck waiting on a Google login before the good part.

---

## Part 0 — The four pieces (3 min)

**Goal:** give them one mental model they can hang everything else on.

**Say:**
> "You've probably used Claude, or ChatGPT, as a chat window. You ask, it answers, and next week it's forgotten you exist. Today we're building something different: an *agent* — closer to a very literal personal assistant.
>
> Any assistant needs four things. A **desk** to work at. A **notebook** — what it knows about you and what it was in the middle of. **Hands** — access to the things it's helping with, like your calendar. And an **alarm clock** — so it does things without you having to ask.
>
> That's the whole class. Four pieces. We'll build them one at a time."

**Show:** the four-pieces table from the README on screen. Leave it up or come back to it at every part ("that was the desk, now the notebook…").

**Why this matters:** non-technical people get lost when every step feels like a new random setting. The four pieces turn 30 minutes of clicking into one story.

---

## Part 1 — Open Claude Desktop, start a Claude Code session (2 min)

**Do:** open the Desktop app. Show the regular chat, then switch to **Claude Code**.

**Say:**
> "Same Claude you know, but this mode can work *with files on your computer* — read them, write them, keep them up to date. That's what lets it have a notebook. Regular chat can't do that."

**Don't** explain what Claude Code is "for programmers." If someone asks: *"It started as a coding tool. It turns out a tool that's good at managing files and following instructions is also good at running your life admin."*

**Checkpoint:** everyone sees the Claude Code start screen.
**Catch-up:** "If you don't see it, you may need to update the app or your plan doesn't include it — follow along on screen, the starter kit will get you there after."

---

## Part 2 — Give it a desk: the workspace folder (3 min)

**Do:** create a new folder in Documents. Name it after the **job**: `MorningBrief`, `EmailHelper`, `MoneyCheck`.

**Say:**
> "This folder is the agent's desk. Everything it knows and everything it produces lives here. One agent, one folder. If you build a second agent later, it gets its own folder — just like you wouldn't share one desk between your accountant and your personal trainer."

**Tip to say out loud:** *"Name it after what it does, not 'Claude stuff.' In three months you'll have three of these, and you'll thank yourself."*

**Checkpoint:** everyone has an empty folder with a job-name.

---

## Part 3 — Local or Cloud? (4 min)

**Goal:** they understand *why* we pick Local today, and what Cloud is for — so the schedule step in Part 6 makes sense.

**Do:** show where the session lets you choose. Pick **Local**, then select the folder from Part 2.

**Say:**
> "Claude can work in two places. *Local* means on your laptop, at the desk we just made. *Cloud* means on Anthropic's computers, somewhere else."

**Show this table:**

| | **Local** (today) | **Cloud** |
|---|---|---|
| Where it runs | Your laptop | Anthropic's servers |
| Sees the folder on your computer? | ✅ Yes — that's the point | ❌ No — it only sees what's online: connected accounts, or a project stored on GitHub |
| Needs your laptop on? | ✅ Yes, and the app open | ❌ No — runs while you sleep |
| Good for | Working *with* it; anything private you'd rather keep on your machine | Jobs that must happen even when your laptop is closed |
| Setup for a beginner | Easy — pick a folder | Harder — its "desk" has to live online |

**The rule of thumb to give them:**
> "Start Local. Always. It's easier, and you can see everything it does. Graduate to Cloud only for a job that genuinely has to run while your laptop is closed — and by then you'll know exactly what you want it to do."

**Why this matters (for you, the trainer):** the single most common confusion later is *"my cloud schedule ran but it didn't know anything about me."* That's because a cloud run can't see a folder on someone's laptop. If you plant that idea here, Part 7 is easy.

**Checkpoint:** everyone has a Local session open, pointed at their folder.

---

## Part 4 — Give it a notebook: three files + the interview (6 min)

This is the heart of the class. Slow down here.

### 4a — The three files (2 min)

**Say:**
> "Here's the secret most people miss. Claude, every time it starts, automatically reads **one** file in its folder: `CLAUDE.md`. That's its job description. Anything else, it only reads if the job description tells it to."

**Show:**

| File | Plain-English | Analogy | Changes… |
|---|---|---|---|
| `CLAUDE.md` | Who it helps, how it behaves, its hard rules — and "always read the other two files" | Job description | Rarely |
| `memory.md` | Facts about you: preferences, people, recurring things, decisions | Notebook | When facts change |
| `progress.md` | Where things stand right now and what's next — nothing else | Sticky note on the desk | Every run, **replaced**, not added to |

**The line that makes the whole system work** — show it in the `CLAUDE.md`:

```markdown
## Always load
@memory.md
@progress.md
```

> "Those two lines tell Claude: *every time you start, also read these.* Without them, your notebook is just sitting in a drawer."

### 4b — Don't write them yourself. Let it interview you. (4 min)

This is the "aha" moment of the class. Have everyone type this into their session:

```
I'd like you to be my [morning brief / email / money] assistant.
Before we start, interview me — one question at a time, no more than
8 questions — to learn what you need to know to do this well.
When we're done, create three files in this folder:
- CLAUDE.md: short instructions and hard rules for this job, and
  load memory.md and progress.md using @ imports
- memory.md: the facts you learned about me
- progress.md: "Current state" and "Next step" only
Show me each file before you save it.
```

**Say while it runs:**
> "Notice: you didn't write a single file. You just had a conversation. It wrote its own job description and notebook — and asked permission before saving. *That's* the pattern you'll use forever: talk to it, let it write things down, check what it wrote."

**Warn them before it happens:** "The first time it wants to create a file, it'll ask permission. That's good. Click allow."

**Checkpoint:** three files exist in their folder. Have them open `memory.md` in the folder and read it.
**Catch-up:** "If the interview stalled, copy the three files from the starter kit for your scenario — they're pre-filled, just edit the facts."

**Prove it worked:** start a **new** session in the same folder and ask *"What do you know about me?"* It answers from `memory.md`. This is the moment they believe it.

---

## Part 5 — Give it hands: one connector (4 min)

**Do:** add one connector — Google Calendar is the safest demo (looking at a calendar can't break anything). Gmail second.

**Say:**
> "A connector is a pair of hands into one of your accounts. You sign in once with the normal Google sign-in — you never type a password into Claude, and nothing goes in a text file."

**Teach the three levels of hands** (they'll use this vocabulary for the rest of their life with agents):

| Level | It can… | Example | Start here? |
|---|---|---|---|
| 👀 **Look** | Read only | "What's on my calendar tomorrow?" | ✅ Yes |
| ✍️ **Draft** | Prepare something for you to approve | "Draft a reply to Sam" | After a week |
| 🖐️ **Act** | Do it without asking | "Send it" | Only for low-stakes things, and only with a rule in `CLAUDE.md` |

**Test it immediately** — have everyone ask:
```
What are my next three calendar events? Use what you know about
me from memory.md to tell me which one matters most.
```
That one prompt shows **hands + notebook working together**. Point that out.

**Checkpoint:** the agent answers with real events.
**Catch-up:** "If your account wouldn't connect, skip to Part 6 — your agent still works with the folder, you'll connect it at home."

---

## Part 6 — Give it an alarm clock: a schedule (5 min)

### 6a — Two kinds of alarm clock (1 min)

Tie back to Part 3:

| | **Scheduled task** (local) | **Routine** (cloud) |
|---|---|---|
| Runs on | Your laptop, with the Desktop app open | Anthropic's servers |
| Laptop asleep? | Skips that run (or catches up when it wakes) | Runs anyway |
| Reads your folder & notebook? | ✅ Yes, automatically | Only if the notebook lives online (GitHub, Notion, Drive) |
| Today | ✅ We use this | Shown, not built |

### 6b — Writing the instruction (2 min)

**Say:**
> "A schedule is just a message you'd normally type, set to send itself. So the only skill is writing that message well."

**Show the formula** (it's on their handout):

> **WHEN** it runs → **WHAT** to look at → **WHAT** to produce → **WHERE** to put it → **WHAT NOT** to do → **UPDATE** progress

**Bad vs good:**

❌ *"Check my email."*

✅
```
Every weekday at 8:00:
Look at today's calendar and anything in my inbox from the last
16 hours. Using what you know about me in memory.md, write a
brief of no more than 10 lines — time-sensitive items first.
Save it as briefs/today.md and show it to me.
Do not reply to, archive, or accept anything.
Then replace progress.md with today's state and anything I need
to follow up on tomorrow.
```

> "Every line in that second version prevents a real problem. No time window — it reads your whole inbox. No length limit — you get an essay. No 'do not' — it might helpfully archive something. No progress update — tomorrow it starts from zero."

### 6c — Run it once by hand, then schedule it (2 min)

**Do:** paste the instruction into the session and run it **now**, by hand. Look at the output together. Then set it as a scheduled task.

**Say:**
> "Never schedule something you haven't watched run once. If it does something odd while you're watching, it'll do something odd at 8am while you're not."

**Warn them about the one thing that silently breaks schedules:**
> "If the scheduled run hits a permission question — 'can I save this file?' — and you're not there to click allow, it just waits. When you ran it by hand just now and it asked for permission, choose the option that *remembers* that permission for this folder."

**Checkpoint:** a scheduled task exists. **Optional wow:** set one to run in 2 minutes and watch it fire before the class ends.

---

## Part 7 — Bonus: make every run remember (4 min)

*Cut this part first if you're short on time.*

**Goal:** they see *why* the notebook + schedule together are more than the sum of their parts.

**Say:**
> "Here's what happens every time that alarm goes off:"

```
⏰ 8:00 — scheduled task starts, in your folder
   ↓
📄 reads CLAUDE.md  → "I'm your morning brief assistant, here are my rules"
   ↓  (@ imports)
📓 reads memory.md  → "Sean is in Dublin, standup is Mondays at 10"
📌 reads progress.md → "Yesterday I flagged the client call moved to 2pm"
   ↓
🤝 uses connectors  → looks at today's calendar and inbox
   ↓
✍️  writes the brief → briefs/today.md
   ↓
📌 replaces progress.md → "Today's state, tomorrow's follow-ups"
```

> "That last step is what makes it an assistant instead of an alarm. Tomorrow's run starts where today's left off. Over a few weeks, it's tracking things you'd forgotten you asked about."

**For the curious — making a *cloud* routine remember:** it can't see the laptop folder, so the notebook has to live somewhere online that the routine can reach: a GitHub repository (the clean way — the routine runs inside it), or a Notion page/Google Doc it reads and updates via a connector (the no-code way). Name this as the "next class" topic rather than doing it live.

### Optional add-on: one skill (if the room is fast)

**Say:**
> "Once you notice yourself asking for the same thing the same way, save it as a *skill* — a recipe card. It lives in a hidden folder called `.claude/skills/`, and Claude pulls out the right recipe when the job matches."

Show `starter-kits/morning-brief/.claude/skills/morning-brief/SKILL.md` on screen. Point out it's just plain English with a name and a "use when…" line at the top.

**Tip:** the `.claude` folder is hidden. On a Mac, press **Cmd + Shift + .** in Finder to show hidden files; on Windows, View → Show → Hidden items.

---

## Part 8 — Wrap-up: your first week (2 min)

**Say:**
> "Four pieces: desk, notebook, hands, alarm clock. Everything you build from here — more agents, more connectors, more schedules — is just more of the same four pieces."

**Give them the first-week plan** (also on the handout):

| Day | Do this | Why |
|---|---|---|
| 1 | Let today's schedule run. Read the output. | See it work without you |
| 2 | Correct one thing: "Remember that I…" | Watch `memory.md` change |
| 3 | Open `progress.md`. Is it a short sticky note, or a growing diary? | Catch the #1 mistake early |
| 4–5 | Ask it to do one thing differently; let it update `CLAUDE.md` | Tune the job description |
| 6 | Notice anything you've asked the same way 3 times → "save that as a skill" | Your first recipe |
| 7 | Read all three files yourself. Delete anything stale. | Five minutes of housekeeping prevents weeks of drift |

**Close with:**
> "Don't add a second connector or a second schedule until the first has run cleanly for a week. The people who get the most out of this are the ones who start boring."

---

## Appendix — When something breaks live

| What they see | What to say / do |
|---|---|
| "It says it can't access my calendar" | Connector not authorized in this session, or a work account blocking it. Re-check Settings → Connectors; try a personal account. |
| "It forgot what I told it" | It was said in chat but never written down. Ask: *"Save that to memory.md."* Teach the phrase **"remember that…"** |
| "It created a file somewhere weird" | Session isn't pointed at their folder — check the folder shown for the session. |
| "My `CLAUDE.md` exists but it ignores memory.md" | The `@memory.md` lines are missing. Add them. |
| "The schedule didn't run" | Laptop asleep / app closed, or it's stuck on a permission prompt. Open the app and check the task's last run. |
| "It's asking permission for everything" | Normal for the first session. Choose the "allow for this folder" option when offered. |
| "Is this safe?" | See `faq.md` — but the short version: it can only touch what you connect, it asks before acting, and you set the hard rules in `CLAUDE.md`. |
