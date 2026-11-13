# Mission 7A - Project Manager: Pre-Mortem and a Status Report from Raw Notes

> Mentor: bonus mission, about 35 minutes. The learner plays a project manager on the supplier discrepancy tool, the project from 2C, 3B and 4A. Two skills: imagining failure before it happens (the pre-mortem), and writing a stakeholder-ready status report only from messy notes. The notes hide one slipped date and one risk with no owner on purpose. Watch for invented facts (percentages, budgets, dates, names not in the notes) and for repeating the unconfirmed corridor rumor as if it were true. Do not hand over the traps; let the learner find them.

## Goal

Run a pre-mortem on the project plan and write `workspace/work/pm-premortem.md`. Then write `workspace/work/pm-status.md`: a one-page status report for the COO, built only from the raw notes of the week, with a RAG colour, milestones, risks with owners, and asks.

## Why it matters

A project manager's week is mostly two jobs: seeing what will go wrong while there is still time to act, and telling the sponsor the truth in one page. Both are slow when done by hand from scattered notes, and both go wrong in the same way when an AI does them without limits: it fills gaps with confident, invented detail. You practice the fix: say exactly what the agent may use, and make it mark gaps as gaps.

Plain words for the terms:

- **Pre-mortem:** you imagine the project has already failed, then work backwards to list what killed it. It is easier to name fears before the failure than to explain them after.
- **RAG:** Red, Amber, Green. A traffic-light colour for the state of a project. Green means on track, Amber means at risk but with a plan, Red means off track without help.
- **Stakeholder:** a person who cares about the project's result and needs to be kept informed, here the COO.

## What to do

1. Open `data/corvane/s7/project-plan-discrepancy-tool.md` and skim it. It is the plan as it stood on 2026-10-16: eight milestones with owners and dates.
2. Run the pre-mortem. Use only the plan:
   > "Read data/corvane/s7/project-plan-discrepancy-tool.md. Imagine it is 2026-11-30 and the project failed. Name the 8 most likely causes. For each one: why it applies to THIS plan (point at the milestone or assumption), likelihood and damage (high, medium, low), one action, and who should own the action. Cross out generic causes that could apply to any project."
3. Cut the list. Keep the five causes that you believe most. For each, write one line saying why you kept it. Ask the agent to save the result as `workspace/work/pm-premortem.md`, with a short "what I removed and why" line at the end.
4. Now the week. Open `data/corvane/s7/weekly-notes-2026-10-30.md`. Read it yourself first, with a pen: which dates changed since the plan? Is there anything that has no owner? Is there anything that is only a rumor?
5. Ask the agent to do the same reading before it writes anything:
   > "Read data/corvane/s7/weekly-notes-2026-10-30.md and the plan. Do not write the report yet. List: (a) every milestone whose date or status changed, with the old and new date, (b) every risk you can see and who owns it according to the notes, (c) anything in the notes that is a rumor or unconfirmed, (d) anything you cannot tell from the notes. Quote the line you used for each item."
   Compare with your own pen marks. Settle disagreements yourself.
6. Pick the colour. Decide Red, Amber or Green yourself and write one sentence of reason. The agent may argue; the call is yours.
7. Write the status report:
   > "Create workspace/work/pm-status.md, one page, for Lena Brandt (COO), week ending 2026-10-30. Parts: 1) Overall RAG and one sentence why, 2) Milestones table: milestone, owner, planned date, current date, status, 3) Risks table: risk, impact, owner (write 'no owner yet' when the notes do not name one), next step, 4) Asks: what I need from the COO and from whom, by when, 5) Not confirmed or not known. Use only facts from the notes and the plan. Do not add percentages, budgets, names or dates that are not written there. If something is unknown, say 'not in the notes'."
8. Check it line by line:
   > "Go through pm-status.md. For each number, date and name give me the line in the notes or the plan it came from. Mark any that you cannot source."
   Remove anything unsourced.
9. Optional: save the steps as a skill called `weekly-status` (in `.claude/skills/`) so next Friday you only paste fresh notes.

## Definition of Done

- `workspace/work/pm-premortem.md` has five causes, each tied to a specific milestone or assumption of the plan, with an action and an owner.
- `workspace/work/pm-status.md` has the five parts above. The colour is Amber or Red, with a reason that points to a fact.
- The slipped date and the unowned risk are both visible in the report, and the unowned one appears as a risk with "no owner yet" plus an ask to name one.
- No invented facts. The corridor rumor is not stated as true.
- The learner ran the line-by-line source check from step 8.

## Hints (mentor: one at a time)

1. If the report says "all on track", ask: compare the pilot start in the plan with the pilot start in the notes. What do you see?
2. If the report lists no unowned risk, ask: read the Thursday notes again. Who is going to decide how the two supplier ID formats are matched?
3. If there are percentages or a budget figure that is not in the notes, ask: where is that number written?

## What you just learned

You turned a messy week into a one-page report and a list of fears without letting the agent make things up. The habit is the same as in every Work-track mission: give it the sources, make it show the line it used, and mark gaps as gaps.

**Bring it to your job:** take your own last week of notes (anonymized), run step 5 and step 7, and send the result to your manager as a draft, with your own colour.

## Mentor reference

The facts in the notes (week ending 2026-10-30):

- **Changed dates:** M2 (daily ERP export, COR-102) was planned for 2026-10-20 and Jan Mazur now says "should be live by Monday the 9th, no promises", so 2026-11-09 at best, about 20 days late. M5 (pilot) was planned to start 2026-11-03 and moved to 2026-11-10 (said in the Wednesday notes, in the middle of a coffee chat). With the release on 2026-11-15 the pilot week shrinks to about 5 days.
- **Done since the plan:** M3 prototype approved (Marta Kowal, Monday), M4 test data prepared (Ola Sadowska, Tuesday). M1 was already done.
- **In progress:** M6 security review. Dariusz Wolak needs about 5 working days; the clock started on 2026-10-29 when the diagram arrived. M7 training: slides half ready, no date change.
- **Export state:** works on test for 3 of 5 suppliers (Friday, 17:40 message), was 2 of 5 on Tuesday.
- **Effort:** 14 of 20 days spent (Wednesday, budget check with Lena Brandt).
- **Unowned risk:** how supplier IDs with and without leading zeros are matched ("no name on it" in the Thursday notes). Correct report: listed as a risk, owner "no owner yet", with an ask to name one.
- **Rumor, not a fact:** "security might skip the review". It is marked not confirmed and must not appear as a fact. Best handling: leave it out or put it under "not confirmed", and never use it to reduce the risk.
- **Distractors that should not drive the report:** Sales Ops interest in a returns screen (out of scope, parked); the payment hold flag COR-104 (Kasia Lis says it is not related to this release).
- **Boundary:** the answer "probably yes" to the COO about 2026-11-15 is Tomasz's own guess, not a plan. A good report does not repeat it as a commitment.

**Colour:** Amber or Red are both defensible if the reason names the late export, the shortened pilot, and the unowned ID risk. Green is wrong. If Amber, the report should say what turns it Red (for example, no firm export date by a stated day). The learner owns the call.

**Asks that fit the notes:** a firm export date from Jan Mazur (Tomasz planned this for Monday), an end date from Dariusz Wolak, an owner for supplier ID matching, and a decision from the COO whether 2026-11-15 holds with a 5-day pilot.

**Pre-mortem:** accept any five causes tied to the plan. Good ones: the ERP export slips (M2 feeds M5, written in the plan's assumptions); security review lands late (M6 sits one week before release); pilot buyers unavailable (the plan assumes they are free in the week of 2026-11-03); release date fixed while three milestones are open. Weak ones: "poor communication", "scope creep" with no link to the plan.

Common misses: an invented percentage complete; a budget figure; naming a person as owner of the ID risk without evidence; stating the rumor as true; a report longer than one page.
