# The Work Case: Corvane Supply

This is the world of the **Work track**. The Signal track (in `THE-CASE.md`) is a startup story. This one is about a normal company with normal, repetitive office work: invoices, meeting notes, requirements, reports, policies. If you came here after a live group session, this is your practice ground.

Everything here is fictional. The company, the people, the suppliers, and all numbers are made up for training.

---

## The company

**Corvane Supply** is a regional wholesale distributor based in Poznań, Poland. About 400 people. It buys packaging, paper, and cleaning products from suppliers in Poland and Germany, and sells them to hotels, restaurants, offices, and small retail chains.

Corvane runs on an old ERP system, many Excel files, email, and a task tracker. Nothing is broken, but a lot of skilled people spend hours a week copying numbers between files, writing the same kinds of documents, and chasing the same kinds of answers.

## Your role

You just joined Corvane's **AI working group**: a small team the COO set up to find out where AI agents can take real hours off people's weeks. You are not a developer. You are an analyst, project manager, or operations person, like most of the people you will help.

Your job is to take one real chore at a time, do it with an AI agent, and leave behind something reusable: a file, a skill, a reviewer, a report, a prototype.

## The people you work with

- **Lena Brandt, COO.** Sponsor of the AI working group. Wants hours saved and fewer errors, not demos.
- **Marta Kowal, Head of Supplier Reconciliation.** Her team checks every supplier invoice against what was ordered. They find mistakes by eye, in Excel, late in the month.
- **Irene Holt, Senior Business Analyst.** Writes requirements (BRDs) after long calls with the business. Her bottleneck is turning a 40-minute call into a clean document.
- **Tomasz Wren, Project Office lead.** Owns the change-request (CR) process. Every Friday he builds a status report by hand from a tracker export.
- **Paweł Nowicki, Operational Excellence.** Owns company policies and process rules. Gets the same questions about them every week.

## The project everyone is circling

Marta's team wants a **supplier discrepancy tool**: something that catches price and quantity mismatches between invoices and purchase orders before payment, shows them on one screen, and lets the team resolve them with a comment trail. Irene is writing the requirements. Tomasz is tracking it as a change request. You will touch it from every side.

## What you have to work with

Everything lives in `data/corvane/`, one folder per session:

- `s1/` - three supplier invoices (PDF), the matching purchase-order export, and five regional customer files that need merging.
- `s2/` - two meeting transcripts and a short BRD template.
- `s3/` - a task-tracker export with change requests, a list of twelve data items to sort by risk, and a draft connection file with a planted problem.
- `s4/` - a draft BRD with problems in it, and a requirements pack to check for contradictions.
- `s5/` - a 30-day pilot card template.
- `s6/` - a folder of Corvane policies.
- `s7/` - a project plan and raw weekly notes for the supplier discrepancy tool, a release plan, and a note on teams and dependencies.

## How the Work track is organized

The track follows the order of a live group program: one folder per session in `sessions/`. Each session has a core mission (about 30 minutes) and one or two stretch missions. Your finished work goes into `workspace/work/`.

| Session | Theme | Core mission | Stretch |
|---|---|---|---|
| 1 | Context, agent vs chat, plan-build-check | 1A Invoices to a checked spreadsheet | 1B Merge five messy files |
| 2 | Skills and the verifier pattern | 2A Meeting transcript to follow-up, then a skill | 2B Verifier skill, 2C Transcript to BRD |
| 3 | Outside data: MCP, API, script | 3A Exchange-rate skill and spend report | 3B Weekly change-request report, 3C Safe access note |
| 4 | Prototype, roles, subagents | 4A BRD to clickable prototype | 4B Reviewer subagent, 4C Parallel consistency check |
| 5 | Memory and your working system | 5A Project memory file, 5B Your own 30-day pilot | 5C Cost, tokens and rollback, 5D Demo day and 90-day plan |
| Bonus | Documents as agent knowledge | 6A Read-only policy researcher | |
| Bonus | Roles and automation | 7A Project Manager: pre-mortem and status, 7B Technical Project Manager: dependencies and release risks | 7C Proactive agent, 7D Telegram bot (optional) |

The 5B mission leaves Corvane behind: you pick a chore from your own job and plan the next 30 days around it. That is the point of the whole track. 5D builds on it: a 3-minute demo and a 90-day plan, also about your own job.

## In the open live group? Use this table

The table above follows the 5-session team program. The open live group at [AISandboxLab.com](https://aisandboxlab.com/en) has 6 sessions in a different order, and the sixth is a demo day. If you are in that group, find the session you just had here and start with its core mission. Tell your mentor "I'm in the open group, we just had session 3" and it will open the right one.

| Your live session | Theme | Core mission | Stretch |
|---|---|---|---|
| 1 | From chat to tool | 1A Invoices to a checked spreadsheet | 1B Merge five messy files |
| 2 | An idea becomes a plan and a prototype | 4A BRD to clickable prototype | 2C Transcript to BRD |
| 3 | Memory, skills and your own agents | 2A Meeting transcript to follow-up, then a skill | 2B Verifier skill, 5A Project memory file, 4B Reviewer subagent, 7C Proactive agent |
| 4 | Connecting services (MCP) | 3A Exchange-rate skill and spend report | 3B Weekly change-request report, 3C Safe access note |
| 5 | MVP and publishing | 5P Save and publish your prototype | 5C Cost, tokens and rollback, 4C Parallel consistency check, 7D Telegram bot |
| 6 | Demo day and AI at work | 5B Your own 30-day pilot, then 5D Demo day and 90-day plan | 6A Read-only policy researcher |

5P has no folder of its own: it reuses the steps of Signal missions 09 (save with git) and 10 (go live) on your 4A prototype. For the open group, publishing is the expected result of session 5: the site promises a live MVP you can open by link. Skip it only when you cannot create a hosting account (for example because of a work laptop policy), and the reason is written down under "Notes from your mentor".

## Practice by your role

Pick the missions that match your job first, then go wider.

| Your role | Start with |
|---|---|
| Business Analyst | 2C, 4A, 4B |
| Project Manager | 3B, 7A |
| Technical Project Manager | 7B, 4C |
| Product Manager | The Signal track (missions 03 to 08) |

7C and 7D (a report that runs by itself, and an optional Telegram bot) suit anyone who builds a weekly report or answers the same question again and again.
