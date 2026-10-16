# Tips — For Trainers and for Attendees

## The two mistakes that cause almost everything else

1. **`progress.md` becomes a growing log instead of a snapshot.**
   Overwrite it every session: "here's where things stand, here's what's next." The moment it starts reading like a diary, the agent has to wade through old noise to find today's one fact — and eventually it misses it. If you only remember one tip from this whole page, make it this one.

2. **`CLAUDE.md` becomes a dumping ground for facts.**
   One-off facts ("the client's name is X," "we decided Y") belong in `memory.md`, not `CLAUDE.md`. The test: *if it might change later, it's memory, not instructions.* `CLAUDE.md` should stay short enough to reread in full every single time — the moment it's 500 lines, the agent starts skimming instead of reading.

---

## Setting up

- **Start with one connector, not five.** It's tempting to connect everything on day one. Don't — if something breaks, you won't know which connector caused it.
- **No folder structure beyond the three files**, until the agent is actually producing something worth keeping (a report, an export, a generated document). Build structure when you need it, not before.
- **Name the folder after the job, not the tool.** `MorningBriefAgent`, not `ClaudeFolder`. You'll likely end up with more than one agent eventually, and generic names get confusing fast.
- **Test a schedule manually before you schedule it.** Run the exact instruction once in a normal chat first. If it doesn't do what you want when you're watching, it won't magically do better unattended.

## Writing the three files

- **`CLAUDE.md`** — instructions and hard rules only. Good test: "would this still be true in six months?" If not, it's not instructions, it's a fact — put it in `memory.md`.
- **`memory.md`** — flat, one file, append or edit as facts change. Update existing lines rather than adding new ones that contradict old ones. A stale fact is worse than no fact — the agent will confidently act on the wrong one.
- **`progress.md`** — two sections, always: *current state*, *next step*. When you open it, it should answer "where did we leave off?" in ten seconds, not require reading five paragraphs.

## Local vs. cloud, in practice

- Use **local** (Claude Desktop, workspace open) for anything you want to sit and work on together, or anything touching files you don't want leaving your machine.
- Use **cloud** (a schedule/routine) for anything that should just *happen* on a cadence — whether or not you're at your laptop.
- They're not two different products — the same workspace folder and the same three files work for both. A schedule is just the agent running itself without you present.

## Privacy and safety basics

- Don't paste real passwords, API keys, or full account numbers into any of the three files — they're plain text. Use the connector's own sign-in flow for credentials; it won't ask you to write a password into a text file.
- For anything that takes an action with real consequences (sending an email, moving money, posting publicly), put a hard "never do X without asking me first" rule in `CLAUDE.md` — see the Email Agent and Finance Advisor scenarios for the exact wording.
- If a demo account is in any doubt, use a sandbox/test account rather than a real one on stage.

## When something seems "off"

| Symptom | Likely cause |
|---|---|
| Agent seems to have forgotten something you told it | Check `memory.md` — was it actually saved there, or just mentioned in chat and never written down? |
| Agent repeats the same action every scheduled run instead of progressing | Check `progress.md` — is it actually being overwritten with the new state, or stuck/empty? |
| Agent follows some instructions but not others | `CLAUDE.md` may have grown too long — trim it back to the handful of rules that actually matter |
| Scheduled run didn't do anything useful | Confirm the schedule is pointed at the right workspace folder (Part 6 of the training script) and that the connector it needs is still authorized |

## For attendees, after the session

- Pick one scenario from the Scenarios doc and actually build it this week — the pattern doesn't stick from a single demo.
- Resist adding a second connector or a second scheduled task until the first one has run cleanly for a few days.
- Come back to `memory.md` and `progress.md` about once a week and actually read them — if they don't make sense to *you* anymore, they won't make sense to the agent either.
