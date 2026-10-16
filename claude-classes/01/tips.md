# Tips — Building Agents That Keep Working After Week One

Most first agents work beautifully on day one and quietly get worse by week three. Almost always for the same handful of reasons. This page is those reasons, and how to avoid them.

---

## 1. The five golden rules

1. **One agent, one folder, one job.** "Email helper" — yes. "Email, finance and my diet" — no. When it does three jobs, it does all three badly and its notebook becomes a mess.
2. **`CLAUDE.md` must load the other two.** Claude only reads `CLAUDE.md` on its own. Without `@memory.md` and `@progress.md` in it, the notebook sits in a drawer.
3. **`progress.md` is a sticky note, not a diary.** Replace it every run. Never append.
4. **Facts go in `memory.md`, not `CLAUDE.md`.** If it might change someday, it's a fact.
5. **Watch it once before you schedule it.** If it's odd while you watch, it's odd at 8am while you don't.

---

## 2. Writing `CLAUDE.md` — the job description

**The test for every line:** *"Will this still be true in six months?"* Yes → it belongs here. No → it's a fact, put it in `memory.md`.

| ❌ Doesn't belong in `CLAUDE.md` | ✅ Belongs in `CLAUDE.md` |
|---|---|
| "My manager is Jordan" | "Anything from my manager goes to the top" |
| "The Acme invoice is due Friday" | "Flag anything about invoices or payments" |
| "We decided to use the blue template" | "Use the template named in memory.md" |
| "Hi Claude! So basically what I'd love is…" (chatty paragraphs) | Short bullets. Imperatives. |

**Hard rules beat polite requests.** "Please try not to send emails" will eventually be ignored. "NEVER send an email. Only create drafts." won't. Use capitals sparingly — for the 2–3 rules that genuinely matter.

**Keep it short enough to read in one breath.** As a rough guide: if it's longer than a page, something in there is actually a fact or a procedure. Facts → `memory.md`. Procedures → a skill.

---

## 3. Writing `memory.md` — the notebook

- **Group it with headings** (People, Recurring, Preferences, …). The agent finds things faster, and so do you.
- **Edit, don't pile up.** If the standup moves from Monday to Tuesday, change that line. Two contradicting lines = it will eventually pick the wrong one.
- **Teach the phrase "remember that…".** Saying it in chat and having the agent write it down is how memory grows naturally. Facts mentioned in passing and never written down are gone next session.
- **Let it ask.** "If you're unsure about something about me, ask, then write the answer in memory.md" is a great line for `CLAUDE.md`.
- **Prune monthly.** Stale facts are worse than missing ones — the agent acts on them confidently.

---

## 4. Writing `progress.md` — the sticky note

Always exactly two sections:

```markdown
# Current state
[Where things stand right now, in a few lines]

# Next step
[What the next run should do or check first]
```

**Why "replace, don't append" matters so much:** a growing log means every run re-reads every previous run's story to find one useful fact. After a month that's dozens of entries of noise, and the one thing that matters today gets missed. This is the single most common way a working agent "loses the plot."

**Quick health check:** open `progress.md`. Can you understand where things stand in 10 seconds? If not, it's become a diary — ask the agent to rewrite it as current state + next step only.

---

## 5. Writing a scheduled instruction

A scheduled task is just a message that sends itself, so the whole skill is writing that message well. Use the formula:

> **WHEN** → **LOOK AT** → **PRODUCE** → **SAVE / SHOW** → **DO NOT** → **UPDATE PROGRESS**

| Missing piece | What goes wrong |
|---|---|
| No time window ("since yesterday 18:00") | It reads your entire inbox history every run |
| No output shape or length | You get an essay you won't read |
| No "do not" line | It helpfully archives / accepts / replies to something |
| No "save to…" | The result only lives in a chat you'll never scroll back to |
| No "update progress.md" | Tomorrow it starts from scratch and repeats itself |

**Once an instruction is longer than ~6 lines, turn it into a skill** and make the schedule one line: *"Run the morning-brief skill."* Easier to read, easier to fix.

---

## 6. Skills — saved recipes

- **When to make one:** the third time you've asked for the same thing in the same way.
- **The easiest way to make one:** after a run you liked, say *"Save how you just did that as a skill called [name], so you do it the same way every time."* Then read what it wrote.
- **The `description` line at the top is the most important line.** It's how Claude decides *when* to use the recipe. Say what it does and when to use it: "…Use when I ask for my brief or when the morning schedule runs."
- **Examples beat explanations.** Three real emails you've written will do more for "write like me" than a paragraph describing your style.
- Skills live in `.claude/skills/<name>/SKILL.md` — a hidden folder. Mac: **Cmd + Shift + .** in Finder. Windows: View → Show → Hidden items.

---

## 7. Connectors — giving it hands safely

**Climb the ladder, one rung at a time:**

| Level | It can… | Stay here until… |
|---|---|---|
| 👀 Look | read | you trust what it notices (a week or so) |
| ✍️ Draft | prepare things for your approval | you've approved most drafts unchanged for a couple of weeks |
| 🖐️ Act | do it without asking | only for low-stakes, easily undone actions — and with a hard rule in `CLAUDE.md` naming exactly what it may do |

- **One connector at a time.** Add the next only when the first has run cleanly for a week. If two are added at once and something breaks, you won't know which.
- **Personal accounts are easier than work accounts.** Many company Google/Microsoft accounts block third-party connections; that's an IT setting, not something you did wrong.
- **Your password never goes in a file.** Connectors sign in through the normal Google/Microsoft page.

---

## 8. Local vs cloud, in practice

| You want… | Use |
|---|---|
| To sit and work through something together | Local session |
| Something private that should stay on your machine (statements, health, documents) | Local session + local scheduled task |
| A daily job, and your laptop is usually open in the morning anyway | Local scheduled task — simplest |
| A job that must run while your laptop is shut (travelling, overnight) | Cloud routine — but its notebook must live online (GitHub, or a Notion page/Google Doc it reads via a connector) |

**The trap:** a cloud routine can't see the folder on your laptop. If your routine "doesn't know anything about you," that's why.

**The other trap:** a local scheduled task skips (or delays) runs while your laptop sleeps. If the 8am brief didn't happen, check whether the laptop was asleep.

**Permission prompts and schedules:** an unattended run that hits *"May I save this file?"* just waits. When you test by hand, choose the option that remembers the permission for that folder, so the scheduled run doesn't get stuck.

---

## 9. Safety basics

- Never put passwords, PINs, full card or account numbers, or ID numbers in any file. Last four digits at most.
- Every agent that can affect the outside world gets a **"NEVER …" rule** in `CLAUDE.md` for its riskiest action (send, pay, delete, post, book).
- Anything involving money, contracts, health or legal matters → *flag for me*, don't act.
- Prefer agents whose worst-case mistake is "a bad draft I didn't send."
- For anything sensitive, keep it **Local** — files stay on your machine.

---

## 10. Keeping it healthy — 10 minutes a week

| When | Do |
|---|---|
| Weekly | Skim the last few outputs. Anything off? Tell it, and say "update CLAUDE.md so this doesn't happen again." |
| Weekly | Open `progress.md` — still a short sticky note? |
| Monthly | Read `memory.md` top to bottom. Delete anything stale. |
| Monthly | Read `CLAUDE.md`. Has it grown? Move facts to memory, procedures to skills. |
| When it "gets worse" | It's almost never the AI changing — it's the notebook drifting. Check the three files first. |

---

## 11. Fix-it table

| Symptom | Most likely cause | Fix |
|---|---|---|
| Forgot something I told it | Said in chat, never written down | "Remember that… — save it to memory.md" |
| Knows nothing about me in a new session | `@memory.md` / `@progress.md` missing from `CLAUDE.md`, or session opened in the wrong folder | Add the imports; check which folder the session is using |
| Repeats yesterday's work | `progress.md` not being replaced | Add "REPLACE progress.md at the end" to the instruction |
| Ignores some rules | `CLAUDE.md` too long or rules buried in prose | Trim; make the important ones short "NEVER…" bullets |
| Scheduled run did nothing | Laptop asleep / app closed, or stuck on a permission prompt | Check the task's last run; pre-approve permissions |
| Cloud routine doesn't know me | It can't see the laptop folder | Keep its notebook in GitHub, Notion or Drive |
| Can't connect Google/Microsoft | Work account restrictions | Try a personal account, or ask IT |
| Output is too long | No length limit in the instruction | Add "under 10 lines" and an example of the shape |
| Skill never gets used | Vague `description` line | Say exactly what it's for and when to use it |

---

## 12. When you're ready for more

- **A second agent** — new folder, new job. Don't bolt it onto the first.
- **Moving to the cloud** — once a local agent has run reliably for a few weeks and you need it while your laptop is closed.
- **Agents that share facts** — a shared `about-me.md` that several agents import with `@`.
- **Approval steps** — have it write a "proposed actions" list you approve before it acts.
