# Your First Personal Agent — Cheat Sheet

## The four pieces

| | Piece | In Claude |
|---|---|---|
| 🗂️ | **Desk** | A folder on your computer — one agent, one folder, one job |
| 📓 | **Notebook** | `CLAUDE.md` · `memory.md` · `progress.md` |
| 🤝 | **Hands** | Connectors — Gmail, Calendar, Drive, Notion… |
| ⏰ | **Alarm clock** | Scheduled task (laptop) or routine (cloud) |

## The three files

| File | What's in it | How often it changes |
|---|---|---|
| `CLAUDE.md` | The job and the hard rules. **Must contain `@memory.md` and `@progress.md`** so it reads them. | Rarely |
| `memory.md` | Facts about you — people, preferences, recurring things | When a fact changes (edit, don't duplicate) |
| `progress.md` | **Current state** + **Next step**. Nothing else. | Every run — **replaced, never added to** |

**Is it a rule or a fact?** Will it still be true in six months → `CLAUDE.md`. Might change → `memory.md`.

## Magic phrases

- **"Interview me, one question at a time, then write the files."** — set up a new agent
- **"Remember that…"** — add to its memory
- **"Update CLAUDE.md so this doesn't happen again."** — fix a behaviour
- **"Save how you just did that as a skill."** — create a recipe
- **"Rewrite progress.md as current state and next step only."** — tidy up

## How much to let it do

👀 **Look** (start here) → ✍️ **Draft** (after a week) → 🖐️ **Act** (only low-stakes, with a "NEVER…" rule)

## Writing a scheduled instruction

**WHEN** → **LOOK AT** (with a time window) → **PRODUCE** (shape + length) → **SAVE / SHOW** → **DO NOT** → **UPDATE PROGRESS**

> *Every weekday at 8:00: look at today's calendar and email since 18:00 yesterday. Write a brief under 10 lines, urgent first. Save it to briefs/ and show me. Don't reply to or archive anything. Replace progress.md with today's state.*

**Always run it once by hand before scheduling it.**

## Local or cloud?

- **Local:** easy, private, sees your folder — but your laptop must be on.
- **Cloud:** runs while your laptop is off — but can't see your laptop folder.
- **Start local.**

## Your first week

| Day | Do |
|---|---|
| 1 | Let it run. Read what it made. |
| 2 | Correct one thing — "remember that…" |
| 3 | Open `progress.md` — still a short sticky note? |
| 4–5 | Ask for one change; let it update `CLAUDE.md` |
| 6 | Asked the same thing 3×? Save it as a skill |
| 7 | Read all three files. Delete anything stale. |

**Don't add a second connector or a second schedule until the first has run cleanly for a week.**
