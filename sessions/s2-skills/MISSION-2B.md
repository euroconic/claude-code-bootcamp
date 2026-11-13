# Mission 2B - A Verifier Skill That Catches What the Writer Missed

> Mentor: stretch mission, about 40 minutes. The learner already has the `meeting-mfu` skill from 2A. Here the follow-up call has three planted problems. Let them run their own skill first and believe the result. The lesson lands when the verifier finds what the writer let through. Do not name the three problems in advance. Use the hints one at a time.

## Goal

Run your `meeting-mfu` skill on the follow-up call in `data/corvane/s2/2026-10-21_reconciliation-followup.txt`. Then build a second skill called `mfu-verify` that checks a follow-up against its transcript and reports every problem. Use it to fix your follow-up.

## Why it matters

An agent that writes a document is a poor judge of its own document. It remembers its own reasoning and reads the result kindly. A second pass with a different job, "find what is wrong", is much stricter. Think of an editor and a proofreader: the author writes, the proofreader only hunts for errors. This is called the **verifier pattern**: one agent does the work, another checks it, and the checker has a short, narrow checklist.

A **skill** loads in two steps. The agent first sees only the name and a one-line description of each skill, like labels on the spines of recipe cards. It pulls the full card out of the drawer only when the job comes up. That is why you can keep many skills without slowing the agent down.

## What to do

1. Read the new transcript with your own eyes for two minutes. It continues the 14 October call: same people, one week later.
2. Run your skill from 2A on it:
   > "Use the meeting-mfu skill on data/corvane/s2/2026-10-21_reconciliation-followup.txt. Save the result to workspace/work/mfu-2026-10-21.md."
3. Read the result as a skeptic. Does every action item have a named owner? Does every item have exactly one date? Does the follow-up agree with the 14 October one, or does something change? Write down what you think is fine.
4. Now create the verifier. Say:
   > "Create a skill called mfu-verify in .claude/skills/mfu-verify/SKILL.md. Its job is to check a meeting follow-up against its transcript. It must: (1) list every action item that has no named owner, (2) list every item that has more than one due date, or dates that conflict, (3) list every claim in the follow-up that cannot be found in the transcript, with no benefit of the doubt, and (4) if I give it a previous follow-up, list every decision that changed compared to it. It never edits the follow-up. It only reports, with the transcript timestamp for each finding, in a table."
5. Run it. Ask for a separate checker, ideally in a fresh session so it has not seen how the follow-up was written:
   > "Use the mfu-verify skill. Check workspace/work/mfu-2026-10-21.md against data/corvane/s2/2026-10-21_reconciliation-followup.txt. The previous follow-up is workspace/work/mfu-2026-10-14.md. Save the report to workspace/work/mfu-2026-10-21-verify.md."
6. Read the report. For each finding, open the transcript at the timestamp and confirm it is real. A verifier can also be wrong.
7. Fix the follow-up for each real finding. For a missing owner, write NO OWNER and keep it visible. For a conflicting date, use the latest date and say it moved. For a changed decision, say what changed and when.
8. Run the verifier again on the fixed file. Repeat until it reports nothing real.

## Definition of Done

- `workspace/work/mfu-2026-10-21.md` exists, built by the learner's `meeting-mfu` skill and then fixed.
- `.claude/skills/mfu-verify/SKILL.md` exists with a name, a description, and the four checks.
- `workspace/work/mfu-2026-10-21-verify.md` exists and names all three planted problems (see Mentor reference), each with a timestamp.
- The fixed follow-up passes a second run of the verifier.

## Hints (mentor: one at a time)

1. Ask the learner to point at one action item in their follow-up and show you the exact transcript line where an owner says "I will". Not every item has one.
2. Ask them to search the transcript for the word "Friday". Then for "thirtieth". What do they notice about one person's task?
3. Ask them to put the 14 October decisions next to the 21 October ones and read the tolerance line in both.

## What you just learned

A skill can be a checker, not only a writer. A short checklist with one job, "find what is wrong, cite the line", gives you a second pair of eyes you can run on every document. You also saw that the agent that wrote something should not be the only one to approve it.

**Bring it to your job:** pick one document you produce regularly, write its five most common mistakes as a checklist, and turn that checklist into a verifier skill.

## Mentor reference

Expected content of `workspace/work/mfu-2026-10-21.md` (facts must match, wording may differ).

**Status of the six kickoff items:**

| Kickoff item | Owner | Status on 21 Oct | Transcript |
|---|---|---|---|
| Register the change request | Tomasz | Done on 2026-10-16, key COR-101, status Backlog | 00:28 |
| Send the mismatch log for three months | Ola | Done on 2026-10-16, about 400 lines | 00:44 |
| Confirm with finance whether payment holds are allowed | Marta | Done: allowed, request 3 working days before due date, written reason per invoice | 01:38 |
| List the top 10 suppliers by mismatches | Ola | Done: Baltic Pack 41, Vistula Paper 33, Norden Clean 29, nobody else above 12 | 01:02 |
| Book the follow-up call | Irene | Done (this call) | 02:32 |
| First BRD draft | Irene | On track, due 2026-10-28 | 02:32 |

**Decisions on this call:**
1. Tolerance is 1% of the line value; the 50 PLN per line rule from 14 October is cancelled (03:21).
2. EUR invoices converted at the NBP rate of the invoice date; this closes a kickoff open question (02:19).
3. Pilot scope stays Baltic Pack and Norden Clean; Vistula Paper is looked at after the pilot month (01:28). This is a confirmation, not a change.

**New action items:**

| What | Owner | Due | Transcript |
|---|---|---|---|
| Update the change request with the new tolerance | Tomasz | 2026-10-22 | 03:57 |
| Re-run the three-month log with the 1% rule, count flagged lines vs the 50 PLN rule | Ola | 2026-10-30 (moved from 2026-10-23) | 04:16, 05:38 |
| Ask the purchasing head who closes a discrepancy | Marta | 2026-10-27 | 05:07 |
| Ask IT whether the ERP can export PO lines automatically, and whether the December upgrade changes the format | NO OWNER | none | 04:28 |

**Open questions still open:** can the ERP export PO lines automatically (04:19); who closes a discrepancy (04:50).

**Risks:** new one: finance needs hold requests 3 working days before the due date (06:08). Unchanged: no capacity in the last week of each month; ERP export format may change after the December upgrade (06:24).

**What the verifier must catch (all three, with timestamps):**
1. **No owner:** the IT question about the ERP export has no owner. Said at 04:28 ("Someone should ask IT about the ERP export"); Irene at 04:43 only keeps it in open questions. Nobody says "I will".
2. **Conflicting dates for one item:** Ola's re-run is due "Friday the twenty-third" at 04:13 and 04:16, then moved to "end of next week, the thirtieth" at 05:25 and 05:38. The follow-up must show 2026-10-30 and say it moved. A follow-up that shows 23 October, or shows both dates without saying which is current, fails.
3. **Reversed decision:** the 14 October follow-up says 50 PLN per line (kickoff 02:31). On 21 October the tolerance becomes 1% of line value (03:21, confirmed 03:31). The verifier, given the previous follow-up, must flag the change. A follow-up that lists both rules as current fails.

**Also acceptable findings (do not mark wrong):** Ola's spreadsheet is now 13 tabs (06:01) as an unused detail; "Told you" at 02:27 is a joke, not a decision.

**Claims the verifier should flag as not in the transcript if they appear:** Vistula Paper added to the pilot; a named purchasing decision; any due date for the IT question; any minimum amount in the 1% rule; the BRD draft date being moved. None of these was said.

**Common misses to push back on:** the coffee machine listed as an item (05:55); the old 50 PLN rule still shown as a current decision; the IT question given to Irene or Marta because "someone has to".
