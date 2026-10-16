---
name: morning-brief
description: Builds my daily morning brief from today's calendar and recent email. Use when I ask for my brief, "what's on today", or when the morning schedule runs.
---

# Building the morning brief

1. **Check progress.md first.** Anything flagged yesterday for follow-up
   goes in the "From yesterday" line — say whether it's resolved.
2. **Calendar:** today's events in my timezone (see memory.md).
   Note anything in the next 2 hours, any clashes, and the longest free block.
3. **Email:** messages since 18:00 yesterday (or since Friday 18:00 on a Monday).
   - Anyone listed under "People whose messages always matter" → time-sensitive.
   - Anything someone is clearly waiting on me for → time-sensitive.
   - Anything under "Never bother me with" → count it, don't list it.
4. **Write it in this exact shape**, 10 lines maximum:

   ```
   ☀️ [Weekday date]

   ⏰ TIME-SENSITIVE
   • …

   📅 TODAY: [n] meetings, free block [time–time]
   📬 Worth a look: [n] · Ignorable: [n]
   ↩️ From yesterday: [item — resolved ✅ / still open ⏳]
   ```
   Leave out any section that's empty.
5. **Save** to `briefs/YYYY-MM-DD.md` and show it to me.
6. **Replace progress.md** with today's state and anything I should be
   reminded about tomorrow.
