---
name: inbox-triage
description: Sorts new email into Needs me / FYI / Ignore and reports it in a short list. Use when I ask to check, sort or triage my inbox, or when an email schedule runs.
---

# Triage

For every message since the last run (see progress.md):

1. **Needs me** — any of:
   - from a VIP in memory.md
   - asks me a direct question or is waiting on my decision
   - a reply on a thread in my "Waiting on" list → also remove it from that list
   - involves money, contracts or anything legal (flag, never draft)
2. **FYI** — useful to know, no action needed (one line each, max 5).
3. **Ignore** — matches "Always safe to ignore" in memory.md. Count only.

For each "Needs me" item that's routine (scheduling, quick confirmation,
thank-you, simple question I've answered before), create a draft with
the `draft-reply` skill.

## Report shape
```
📥 [time] — [n] new

🔴 NEEDS YOU
• [Sender] — [what they want, in 8 words] [✍️ draft ready]

🟡 FYI
• …

⚪ Ignored: [n]
⏳ Still waiting on: [list from memory.md, with days waiting]
```
