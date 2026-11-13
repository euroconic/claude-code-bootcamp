# Session 2 - Skills and the Verifier Pattern

## Theme of the live session

A **skill** is a saved method: a small folder with one instruction file that tells the agent how to do one job your way. Skills live in `.claude/skills/<name>/SKILL.md`.

How skills load, in plain words: the agent does not read every skill in full all the time. At the start it sees only the name and a one-line description of each skill, like the labels on the spines of recipe cards. When your request matches a label, it pulls out that card and reads it. This is called progressive disclosure: little at first, the full detail only when the job comes up. It means you can keep dozens of skills without crowding the agent's attention.

The second idea is the **verifier pattern**: one agent does the work, another checks it. The checker has a different job ("find what is wrong") and a short checklist, so it is stricter than the writer would ever be with its own work.

## Missions

| Mission | What you do | Time | Level |
|---|---|---|---|
| 2A | Turn a messy call transcript into a clean follow-up, then save the method as the skill `meeting-mfu` | 30 min | Core |
| 2B | Build the verifier skill `mfu-verify` and use it to catch planted problems in a follow-up call | 40 min | Stretch |
| 2C | Turn both calls into one business requirements document, with a source on every line | 45 min | Stretch |

Do 2A first. 2B needs the skill you build in 2A. 2C needs both transcripts, not the skills, so it can be done on its own after 2A.

Your finished files go to `workspace/work/`. The case and the people are described in `WORK-CASE.md`.
