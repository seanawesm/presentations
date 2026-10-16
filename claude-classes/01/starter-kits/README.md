# Starter Kits

Three ready-to-use agent folders. Each one works the moment you copy it.

## How to use a kit

1. **Copy** the whole folder (e.g. `morning-brief/`) into your Documents and rename it if you like.
   ⚠️ It contains a hidden `.claude` folder — copy the *folder*, not just the visible files, or the skills get left behind.
2. **Open** Claude Desktop → Claude Code → **Local** → select the folder.
3. **Personalise** — paste this into the session:
   ```
   Read CLAUDE.md, memory.md and progress.md. Everything in square
   brackets [like this] is a placeholder. Interview me, one question
   at a time, to replace every placeholder with real information,
   then show me the updated files before saving.
   ```
4. **Test** — run the first instruction from the kit's `SCHEDULES.md` by hand and check the result.
5. **Schedule** — create a scheduled task with the same instruction.

## What's in each kit

| Kit | Files | Skills | Connectors |
|---|---|---|---|
| [`morning-brief/`](morning-brief/) | CLAUDE.md · memory.md · progress.md · SCHEDULES.md | `morning-brief` | Calendar 👀 · Gmail 👀 |
| [`email-agent/`](email-agent/) | CLAUDE.md · memory.md · progress.md · SCHEDULES.md | `inbox-triage` · `draft-reply` | Gmail ✍️ |
| [`finance-advisor/`](finance-advisor/) | CLAUDE.md · memory.md · progress.md · SCHEDULES.md · `statements/` · `exports/` | `weekly-money-check` | none |

## Seeing the hidden `.claude` folder

- **Mac:** in Finder, press **Cmd + Shift + .** (period)
- **Windows:** File Explorer → View → Show → Hidden items
