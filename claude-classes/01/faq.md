# FAQ — Questions This Audience Always Asks

Short answers you can give from the front of the room. Where an answer depends on someone's plan or settings, say so — don't guess.

---

### "How is this different from just using ChatGPT / Claude chat?"
Chat forgets you between conversations and can only talk. This agent has a **folder** it keeps notes in, so it remembers you; **connectors** so it can look at your real calendar or email; and a **schedule** so it does things without being asked. Same brain, but with a desk, a notebook, hands and an alarm clock.

### "Can it send emails / spend money / delete things without me?"
Only if you connect it at a level that allows that **and** don't forbid it. In this class every agent is set to *look* or *draft* only, and each `CLAUDE.md` has a hard "NEVER send / pay / delete" rule. It also asks permission before changing files. You stay in control by choosing the level (👀 look → ✍️ draft → 🖐️ act) and writing the rules.

### "Is my data used to train the AI?"
It depends on your plan and your privacy settings — show them where the setting is in the app rather than giving a blanket answer. Two things you *can* say: with **Local**, the files in the folder stay on your computer except for what's sent to Claude during a conversation; and connectors only share what the agent actually looks at.

### "What happens if I close my laptop?"
A **local** scheduled task can't run while the laptop is asleep or the app is closed — it'll skip or catch up later. A **cloud routine** runs anyway, but can't see your laptop folder. For most people, a morning task on a laptop that's open in the morning is all they need.

### "Why Local and not Cloud?"
Local is easier to set up, you can see every file it reads and writes, and your private files stay on your machine. Cloud is for jobs that must run when your computer is off — worth it later, not on day one.

### "Do I need to know how to code?"
No. Everything today is plain English — the files are just notes, and you can ask Claude to write them for you. (Claude Code started as a programmer's tool; it turns out "good at managing files and following instructions" is exactly what a personal assistant needs.)

### "What are those `.md` files? Can I open them?"
They're plain text notes ("md" = Markdown, a simple way of writing headings and bullets). Open them in any text editor, Notes, or even Word. Edit them yourself any time — the agent will read your changes next run.

### "It forgot something I told it."
If it was only said in chat, it was never written down. Say **"remember that…"** and check it lands in `memory.md`.

### "Why do I need three files? Can't I just put everything in one?"
You can — and it'll work for about a week. They change at different speeds: rules rarely (`CLAUDE.md`), facts sometimes (`memory.md`), current state every run (`progress.md`). Mixing them is how a file grows until the agent skims it and misses things.

### "What's a skill?"
A saved recipe: step-by-step instructions for one job, so it's done the same way every time. You don't need one on day one. Make one the third time you've asked for the same thing.

### "My work Google account won't connect."
Many companies block third-party connections. That's an IT policy, not an error on your side — try a personal account, or ask IT.

### "How much does it cost?"
It needs a Claude plan that includes Claude Code. Scheduled agents use your plan's usage each time they run — a short daily task is light; ten agents running every hour is not. Start with one agent, once a day.

### "Can I have several agents?"
Yes — one folder each. Resist until the first one has run cleanly for a week.

### "Can it make mistakes?"
Yes — it can misread an email or miscategorise a payment. That's why we start at *look* and *draft*, why outputs go somewhere you read them, and why the hard rules exist. Treat it like a new assistant in their first month: helpful, worth checking.

### "Can my family / team share one agent?"
Not simply on day one — a local agent lives on one person's laptop. Sharing is a cloud setup topic for a later class.
