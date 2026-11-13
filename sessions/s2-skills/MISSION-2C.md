# Mission 2C - Two Calls to One BRD

> Mentor: stretch mission, about 45 minutes. This is Irene's real job: turning a long call into a requirements document. The skill to practice is not writing, it is discipline: every requirement points to a minute of a call, and anything that was not said goes to Open questions. Praise the learner for leaving gaps. Push back on anything that sounds plausible but has no minute behind it.

## Goal

Write a business requirements document (BRD) for the supplier discrepancy tool from both calls, using the short template in `data/corvane/s2/brd-template.md`. Save it to `workspace/work/brd-discrepancy-tool.md`.

## Why it matters

A BRD is the bridge between what the business said and what gets built. If it contains things nobody said, the team builds the wrong thing, and nobody notices until late. An agent is very good at sounding complete. Your job is to make it show where each sentence came from, and to say "not decided yet" where that is the truth.

A **requirement** here means one thing the business needs, written so someone can check it was delivered. **Acceptance criteria** are the checks, like the items on a delivery receipt.

## What to do

1. Open `data/corvane/s2/brd-template.md` and read the rules at the top. Read them aloud to your mentor in your own words.
2. Ask the agent to read both transcripts and plan before writing:
   > "Read data/corvane/s2/2026-10-14_reconciliation-kickoff.txt and data/corvane/s2/2026-10-21_reconciliation-followup.txt. Do not write the BRD yet. First list every business requirement, rule, and open question you can find, each with the file and the minute where it was said. Mark anything you are tempted to add that nobody said."
3. Read the list. Remove anything with no minute. Check two minutes yourself in the transcripts.
4. Now write the document:
   > "Write workspace/work/brd-discrepancy-tool.md using the template in data/corvane/s2/brd-template.md. Every BR must have a source with file, date, and minute. Where a decision changed between the two calls, use the latest version and add one line saying what it replaced. Anything that was not said goes to Open questions. Do not invent screens, roles, numbers, or integrations."
5. Check the sections one by one: is the tolerance the latest one? Are the two pilot suppliers in scope and the others out? Is the success metric a number somebody said, or did the agent make one up?
6. Ask for a self-check, then do your own:
   > "Read the BRD again. Mark every sentence that is not backed by a minute in the transcripts. Do not fix them yet, just list them."
7. Move or delete what does not belong. Save.

## Definition of Done

- `workspace/work/brd-discrepancy-tool.md` exists and follows the template headings.
- Every BR has a source with file, date, and minute, and the minutes are real (spot-check at least three).
- The tolerance rule is 1% of line value, with a line saying it replaced the 50 PLN per line rule.
- Things nobody said are under Open questions, not stated as facts (see Mentor reference).

## Hints (mentor: one at a time)

1. Ask: "Which sentence in your document would you be unable to defend if Irene asked 'where was that said?'"
2. Ask them to look at the two tolerance numbers. Which call came later? Which one goes into the BRD?
3. Ask what the success metric is. Marta said "two and a half days" and "I want those days back" (kickoff 06:44). Did anyone say a target?

## What you just learned

You turned two messy calls into one structured document without letting the agent fill gaps with guesses. The trick is a simple rule, "no minute, no sentence", plus a place for the unknown. That rule works for any document built from meetings, emails, or interviews.

**Bring it to your job:** take your last two real project calls and ask for a BRD, a status summary, or a decision log with a source line on every sentence, then see how many sentences lose their source.

## Mentor reference

Expected shape of `workspace/work/brd-discrepancy-tool.md`. Wording may differ; the facts and citations must match. K = kickoff 2026-10-14, F = follow-up 2026-10-21.

**Background:** the reconciliation team checks supplier invoices against purchase orders by hand at month-end; about 12 tabs in Ola's spreadsheet (K 00:32); two and a half days of three people each month-end (K 00:32); about 14,000 PLN of overcharges found last quarter, found after payment (K 00:32); mismatches are chased for credit notes for two months (K 00:32).

**Goal and success metric:** see mismatches before payment, in one place (K 01:30). No numeric target was given. Marta says "I want those days back" (K 06:44). The numeric target belongs in Open questions.

**Scope in:** pilot on Baltic Pack and Norden Clean for the first month (K 02:00; confirmed F 01:28); one shared discrepancy screen (K 02:51); Ola's Excel kept as backup during the pilot (K 03:04). **Scope out:** other suppliers in the first month; Vistula Paper is to be considered after the pilot month (F 01:28).

**Users:** reconciliation team (Marta, Ola); buyers who look at the same list (K 02:51); Irene as requirements owner, Tomasz as change-request owner (K 03:35). No other roles were defined.

**Business requirements (minimum expected):**
- BR-1 Mismatches between invoice and purchase order are visible before payment (K 01:30).
- BR-2 One shared screen for the discrepancies, replacing emails with attachments (K 02:51).
- BR-3 Differences within tolerance are accepted automatically: 1% of line value (F 03:21). Changed from 50 PLN per line (K 02:31).
- BR-4 Pilot scope is two suppliers for the first month (K 02:00).
- BR-5 EUR invoices are converted at the NBP rate of the invoice date (F 02:19).
- BR-6 A payment hold can be requested for a mismatched invoice, at least 3 working days before the due date, with a short written reason (F 01:38).

**Business rules:** 1% of line value per line; invoice-date NBP rate for EUR; 3 working days for hold requests.

**Open questions (minimum expected):** can the ERP export PO lines automatically every day, and does the December upgrade change the format, no owner yet (K 04:05, F 04:19); who closes a discrepancy, reconciliation or the buyer, Marta asks the purchasing head by 2026-10-27 (K 05:10, F 04:50); numeric success target; screen fields and user permissions; whether comments or a history trail are needed; when Vistula Paper is reviewed.

**Risks mentioned in the calls (may go under Open questions or Background):** no capacity in the last week of each month (K 06:05); ERP export format may change after the December upgrade (K 06:13); hold window of 3 working days is tight at month-end (F 01:55).

**Must not appear as facts (nobody said them):** automatic emails to suppliers; a role or login model; a specific screen layout; an integration with the payment system; a number of days saved as a target; a minimum amount in the tolerance rule.

**Critical check:** the tolerance in the BRD is 1% of line value, with a note that it replaced 50 PLN per line. A BRD that keeps 50 PLN as the rule fails.
