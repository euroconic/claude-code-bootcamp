# Mission 2A - Meeting Transcript to Follow-up, Then a Skill

> Mentor: this is the core mission of session 2. The win has two halves. First the learner gets a clean follow-up from a messy call by working with you step by step. Then they save that method as a skill and watch it do the same job from one short request. Do not let them skip the first half: a skill is only as good as a method they have tried by hand.

## Goal

Turn the kickoff call in `data/corvane/s2/2026-10-14_reconciliation-kickoff.txt` into a meeting follow-up (often called an MFU: meeting follow-up) that a busy manager can read in one minute. Then package the method as a reusable skill called `meeting-mfu`.

## Why it matters

After almost every work call, someone has to write down what was decided, who does what by when, and what is still unknown. It is boring, it gets skipped, and then people remember the call differently. If this takes you 30 seconds instead of 30 minutes, you will actually do it every time.

A **skill** is a saved method: a small instruction file that tells the agent how to do one job the way you like it. Think of it as a recipe card. You write it once, and next time you just say "make the follow-up for this call" instead of explaining everything again.

## What to do

1. Open the transcript and skim the first minute. Notice the noise: train wifi, a parking email, people interrupting each other. That is what real calls look like.
2. Ask your mentor for the follow-up, naming the sections you want:
   > "Read data/corvane/s2/2026-10-14_reconciliation-kickoff.txt and write a meeting follow-up with: a 3-sentence summary, decisions, action items as a table (what, owner, due date), open questions, and risks. Use only what was said in the call. Save it to workspace/work/mfu-2026-10-14.md."
3. Check it against the call yourself. Pick two action items and find them in the transcript by their timestamp. Does the owner match? Does the date match?
4. Ask the agent to check itself: "Go through the transcript again. Did you miss any decision, action item, or open question? Is anything in the follow-up not actually said in the call?"
5. Now save the method as a skill. Say:
   > "Turn what we just did into a skill called meeting-mfu in .claude/skills/meeting-mfu/SKILL.md. It should take any call transcript and produce a follow-up with the same sections, use only what was said, put dates as YYYY-MM-DD, and list anything unclear under open questions instead of guessing."
6. Read the skill file with your mentor. Change one thing so it fits how you work: the language of the output, the order of sections, or a rule like "always name the next meeting date".
7. Test it: start a fresh request, "Use the meeting-mfu skill on the 14 October kickoff call", and compare the new result with your first one.

## Definition of Done

- `workspace/work/mfu-2026-10-14.md` exists with a summary, decisions, an action-item table with owners and due dates, open questions, and risks.
- Its content matches the transcript (see Mentor reference below). Nothing invented.
- `.claude/skills/meeting-mfu/SKILL.md` exists, has a name and a description, and contains at least one rule the learner chose.
- The skill has been run at least once from a short request.

## Hints (mentor: one at a time)

1. A good follow-up is boring on purpose: the same sections every time. Ask them which sections their own manager would want.
2. If owners or dates are missing, the fix is in the prompt: ask for a table with "owner" and "due date" columns, and say "if no owner was named, write NO OWNER".
3. Show them the timestamps: 02:31 is the tolerance decision, 03:19 and 03:27 are two action items. Checking against the source is the habit, not a one-time step.

## What you just learned

You did a job by hand with an agent, checked it against the source, and then turned the method into a skill you can call in one line. That is the basic loop for automating any repeated document: do it once properly, then save the recipe.

**Bring it to your job:** run your new skill on the transcript of your next real work call, and change the skill until its output is something you would actually send.

## Mentor reference

Expected content of `workspace/work/mfu-2026-10-14.md`. Wording may differ; the facts must match.

**Decisions (4):**
1. Pilot covers two suppliers only for the first month: Baltic Pack and Norden Clean (02:00).
2. Tolerance: differences under 50 PLN per line are auto-accepted (02:31).
3. One shared discrepancy screen; Ola's Excel stays as backup during the pilot (03:04).
4. Irene owns the BRD, Tomasz owns the change request (03:35).

**Action items (6):**

| What | Owner | Due |
|---|---|---|
| Register the change request in the tracker | Tomasz | 2026-10-16 |
| Send the mismatch log for the last three months | Ola | 2026-10-16 |
| Confirm with finance whether payment holds are allowed | Marta | 2026-10-20 |
| List the top 10 suppliers by number of mismatches | Ola | 2026-10-20 |
| Book the follow-up call | Irene | 2026-10-21 |
| First BRD draft | Irene | 2026-10-28 |

**Open questions (3):** Can the ERP export PO lines automatically every day? Who closes a discrepancy, reconciliation or the buyer? Convert EUR invoices at the invoice-date or payment-date rate?

**Risks (2):** the team has no capacity in the last week of each month; the ERP export format may change after the December upgrade.

**Common misses to push back on:** the parking email listed as an item; Ola's guess about the NBP rate (05:46) written as a decision; "14,000 PLN of overcharges last quarter" and "two and a half days every month-end" left out of the summary (they are the business case).
