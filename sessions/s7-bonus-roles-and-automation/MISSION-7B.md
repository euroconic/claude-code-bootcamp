# Mission 7B - Technical Project Manager: Dependency Map and Release Risks

> Mentor: bonus mission, about 35 minutes. Same project as 7A, but the view is the release: four teams that must each do something before version 1 goes out. The learner draws who waits on whom and then lists the release risks. Two planted problems: a circular dependency (three parties each waiting for the next one) and a release step with no owner. Let the learner find them by reading the map, not from a hint. An agent that politely lists every dependency in a table can still miss the circle, so push the learner to trace one chain with a finger.

## Goal

Read the release plan and the team notes for version 1 of the supplier discrepancy tool, and write two files in `workspace/work/`: `tpm-dependency-map.md` (who waits on whom, as a table or a simple text diagram) and `tpm-release-risks.md` (release risks with likelihood, impact, owner, and mitigation).

## Why it matters

A technical project manager's job is the space between teams. Each team says "we are on track", and the release still slips, because team A waits for B, B waits for C, and C waits for A, or because a step belongs to nobody. A map makes this visible in ten minutes. The risk list then turns what you see into decisions someone can take.

Plain words for the terms:

- **Dependency:** a piece of work that cannot start or finish until another piece of work is done.
- **Circular dependency:** a loop. A waits for B, B waits for C, C waits for A. Nobody can move first, so the whole loop stands still until a person breaks it.
- **Mitigation:** what you do now to make a risk smaller or less costly.
- **Go / no-go criteria:** the short list of conditions that must be true at the final meeting before release, agreed in advance.

## What to do

1. Open the two files in `data/corvane/s7/`: `release-plan-v1.md` (nine steps with teams, owners and dates) and `teams-and-dependencies.md` (what each team said it is waiting for). Skim both. Notice the teams: the ERP team, Finance Systems, IT security, and the tracker vendor.
2. Build the map in two passes. First the plain list:
   > "Read both files in data/corvane/s7/. List every dependency as one line: 'X waits for Y because Z', and quote the sentence you used. Do not draw anything yet and do not add dependencies that nobody stated."
3. Then the picture. A table is fine, a text diagram is fine:
   > "Create workspace/work/tpm-dependency-map.md. Part 1: a table with columns: step or team, waits for, owner of the thing it waits for, date needed, date promised. Part 2: a simple text diagram with arrows (for example A -> B means A waits for B). Part 3: 'Problems on the map' with every loop, every step with no owner, and every date that arrives after the step that needs it."
4. Check the map yourself. Pick the vendor and trace the arrows with a finger: who does the vendor wait for, and who does that party wait for? Does the chain ever come back to where you started? Compare with what the agent wrote in Part 3.
5. Now the risks. Ask for a first list:
   > "Using the map and data/corvane/s7/release-plan-v1.md, list what could derail the release on 2026-11-15. For each risk: description, likelihood (high, medium, low), impact (high, medium, low), owner (write 'no owner' when the files do not name one), mitigation, and the date by which it must be decided. Use only facts from the files. Also propose go / no-go criteria and three questions for the final meeting."
6. Decide the likelihood and impact yourself. Change at least two of the agent's ratings and write why.
7. Save the result as `workspace/work/tpm-release-risks.md`. Put the highest risks first (high likelihood and high impact), and end with the go / no-go criteria as a draft, marked "to agree with the team".
8. Check:
   > "Go through tpm-release-risks.md. For every date and every name give me the file and line it came from. Which risk has no owner? Which risk would you raise with the COO first, and why?"

## Definition of Done

- `workspace/work/tpm-dependency-map.md` exists with a table, a text diagram or both, and a "Problems on the map" part.
- The circular dependency is found and written as a loop, naming all three parties.
- The step with no owner is named.
- `workspace/work/tpm-release-risks.md` has at least six risks with likelihood, impact, owner, mitigation, and decision date. Ratings reflect the learner's own changes.
- Every date and name in the files comes from the data. A draft of go / no-go criteria is present and marked as a draft.

## Hints (mentor: one at a time)

1. If the map shows only straight lines, ask: take the tracker vendor. Who must act before the vendor, and who must act before that party?
2. If no unowned step is found, ask: look at the last two rows of the release plan table. Whose name is there?
3. If risks contain invented causes (a strike, a budget cut), ask: which file mentions that?

## What you just learned

An agent lists dependencies quickly, but you find the loop by tracing a chain. You also practised the technical project manager's most useful sentence: "this step has no owner, and these three parties are waiting for each other, so someone must break the loop on a named date".

**Bring it to your job:** take the next release or project with more than two teams, write what each team says it waits for, and draw the map before the next status call.

## Mentor reference

**The loop (three parties):**
1. Taskwell (the tracker vendor) will switch on the import interface only after IT security has approved the data terms in writing.
2. IT security (Dariusz Wolak) will approve only after he has the vendor's description of the working interface on the test system.
3. Taskwell will write that description only after the interface is switched on for the test system.

So: Taskwell enable -> waits for security approval -> waits for the vendor's description -> waits for the enable. Nobody can go first. Fix: someone (Tomasz Wren) calls Dariusz Wolak and Nina Falk together and agrees a different first step, for example security reviewing the vendor's written documentation instead of a working system, or the vendor enabling the interface on the test system only, before the approval for production. The fix is a decision for people; the agent may propose it but the learner must say who decides and by when.

**Dates that collide:**
- Vendor enables the interface on 2026-11-04 (R1), security approval planned 2026-11-06 (R2), but R1 waits for R2. So R1 cannot be before R2 as written.
- Daily export (R3) is promised for 2026-11-09 at best. The pilot (R4) starts 2026-11-10. Go / no-go criteria say the export ran 5 days in a row, but the export would have run at most 5 days by 2026-11-14, with no slack, and the go / no-go meeting is on 2026-11-13, so at most 4 days. The criterion cannot be met as drafted.
- Finance (R5) wants to see pilot results before agreeing, and the agreement is planned for 2026-11-11, one day into the pilot.

**The missing owner:** R8 (first week of support) and R9 (rollback) have no team and no owner. Nobody has been named to take questions after release or to decide a rollback. This must appear as a risk with "no owner" and a proposal to name one before the go / no-go meeting on 2026-11-13.

**Other fair risks (from the files):** the release date was set in September and has not moved; both pilot buyers are out on 2026-11-16 and 2026-11-17, the days right after release (support gap); payment hold flag COR-104 stays blocked (Kasia Lis says it is unrelated, so it must not be ranked as a main risk).

**Traps:** inventing an extra team (legal, procurement); treating the vendor date 2026-11-04 as firm; missing the loop because each line looks reasonable alone; giving every risk "high" so the list does not prioritise.

**Strong answer to the last check question:** raise the loop first, because it blocks the vendor and security steps, both before the release, and nobody inside the loop can break it alone.
