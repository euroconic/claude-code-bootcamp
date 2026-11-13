# Mission 5A - Project Memory File

> Mentor: core mission of session 5, about 20 minutes. Teach the four layers (chat, memory file, skills, files) with the whiteboard / handbook / recipe card / archive analogy before touching any file. The strongest moment is the proof: a fresh session that already knows the rules. Warn the learner about `/init` BEFORE they type anything. Do not edit this bootcamp's own `CLAUDE.md` (your own file) under any circumstances.

## Goal

Create a memory file for the Corvane work at `workspace/work/CLAUDE.md`, add one new rule by saying "remember this", and prove that a fresh session in that folder follows it.

## Why it matters

Every new chat starts blank. Without a memory file you re-explain who Marta is, where the data lives, and what the tolerance rule is, every single time. A memory file is the team handbook: the agent reads it at the start of every session, so you explain once.

Four layers, in plain words:

- **Chat = whiteboard.** Wiped when the meeting ends.
- **Memory file = team handbook.** Read at the start of every session.
- **Skills = recipe cards.** One saved method for one job.
- **Files = archive.** The finished work on disk.

> **Warning: do not run `/init` at the bootcamp root.** `/init` is a Claude Code command that writes a memory file for the folder you are in. At the root of this bootcamp that file already exists and it is your mentor's brain. Running `/init` there would rewrite it and your mentor would stop working properly. Create the file in `workspace/work/` only, as described below.

## What to do

1. Check where you are. Ask your mentor:
   > "Which folder am I in right now? Do not change anything."
   It should be the bootcamp root. The new file goes one level down, in `workspace/work/`.
2. Ask the agent to draft the handbook for the Corvane work. Do not use `/init`:
   > "Create the file workspace/work/CLAUDE.md. It is the project memory for my Corvane work. Keep it under 40 lines, in plain English. Sections: Who is who (use WORK-CASE.md: Lena, Marta, Irene, Tomasz, Paweł, one line each), Where data lives (data/corvane/s1 to s6, my results go to workspace/work/), House rules. House rules are: amounts are written with 2 decimals; EUR amounts are converted to PLN at the National Bank of Poland (NBP) rate of the invoice date; the discrepancy tolerance is 1% of line value; never invent requirements, anything not said goes to open questions."
3. Read the file with your mentor. Is anything wrong or missing? Is every line something you would want a new colleague to know on day one? Remove anything that is not.
4. Add a new rule by speaking naturally:
   > "Remember this: every report I produce must end with a line 'Sources:' that lists the files it used."
   Check that the agent put it into `workspace/work/CLAUDE.md` and not somewhere else. If it asks where, say: the project memory in workspace/work.
5. Prove it works in a fresh session. A fresh session means a new conversation that starts empty, so it knows only what the memory file tells it.
   - **Terminal:** close this Claude Code session (type `/exit`). Then type `cd workspace/work` and press Enter, then `claude` and Enter.
   - **Desktop app:** start a new session and choose the folder `workspace/work` as the project folder (File menu or the folder button, then pick `workspace/work`).
   - Note: the agent also reads memory files in the folders above, so you may see your mentor greet you. That is expected. If the mentor behaviour gets in the way, return to your normal session and ask your mentor: "Read workspace/work/CLAUDE.md and answer from it only."
6. In the fresh session ask:
   > "What is our discrepancy tolerance, and how do we convert EUR invoices? Then write a two-line summary of the Baltic Pack carton overcharge from ../../data/corvane/s1/po-export.csv."
   The answer should use 1%, the NBP rate of the invoice date, two-decimal amounts, and end with a "Sources:" line, without you repeating any rule.
7. Go back to your normal bootcamp session (terminal: `cd ../..` then `claude`).

## Definition of Done

- `workspace/work/CLAUDE.md` exists, under 40 lines, with who is who, where data lives, and the four house rules.
- It also contains the new "Sources:" rule, added by saying "remember this".
- The bootcamp root `CLAUDE.md` was not touched, and `/init` was not run there.
- A fresh session in `workspace/work` (or a mentor reading that file explicitly) applied the rules without being reminded.

## Hints (mentor: one at a time)

1. If they ask "what goes in the handbook?", ask: what would you tell a new colleague on their first morning, so they do not have to ask twice?
2. If the rule landed in the wrong file, ask the learner to read both files and find where it went, then move it with a plain request.
3. If the fresh session does not seem to know the rules, read `workspace/work/CLAUDE.md` yourself and check the folder the session was started in. As a fallback, read the file explicitly in your normal session and run the same question there.

## What you just learned

Memory is not magic. It is a short file read at the start of every session. You wrote it once, added a rule by speaking, and a brand new session followed it. You also know where each thing belongs: talk in the chat, rules in the handbook, methods in skills, results in files.

**Bring it to your job:** write a 20-line handbook for one of your real projects (people, where files live, three house rules) and keep it in that project's folder.

## Mentor reference

Expected content of `workspace/work/CLAUDE.md` (wording may differ):

- Who is who: Lena Brandt, COO; Marta Kowal, Head of Supplier Reconciliation; Irene Holt, Senior Business Analyst; Tomasz Wren, Project Office lead; Paweł Nowicki, Operational Excellence.
- Data lives in `data/corvane/s1` to `s6`; results go to `workspace/work/`.
- House rules: 2 decimals; EUR at NBP rate of the invoice date; tolerance 1% of line value (the 21 October call changed it from 50 PLN; the written policy adds a 20.00 PLN minimum); never invent requirements.
- Added rule: reports end with a "Sources:" line.

Fresh session test, expected answer: tolerance is 1% of line value (line value 2,350.00 PLN gives 23.50 PLN; the carton overcharge of 200.00 PLN is above it); EUR converted at the NBP rate of the invoice date; amounts shown with 2 decimals; a "Sources:" line naming `data/corvane/s1/po-export.csv`. Carton: PO price 2.15, invoiced 2.35, 1,000 units, so 200.00 PLN net.

Common misses: the file is too long (copied the whole case); the bootcamp root `CLAUDE.md` was modified; the new rule was written only in chat and not saved.
