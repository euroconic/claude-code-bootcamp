# Mission 4C - Three Checks in Parallel

> Mentor: stretch mission, best after 4B. The idea is that independent checks can run side by side, each in its own room, and one person merges the results. Make sure the learner understands why the checks must not talk to each other before the merge.

## Goal

Check a small pack of three requirement files for contradictions by running three subagents in parallel, one per pair of files, then merge their findings into `workspace/work/consistency-report.md`.

## Why it matters

When requirements are spread over several documents, they drift apart: one file says 1%, another says 50 PLN. Nobody notices until the team builds the wrong thing. Comparing every pair by hand is slow. Three colleagues each comparing one pair, at the same time, is fast.

**In parallel** means at the same time, like three people each reading one pair of documents in separate rooms, instead of one person reading all three pairs in turn.

## What to do

1. Look at the pack: `data/corvane/s4/requirements-pack/` has `features.md`, `use-cases.md` and `acceptance-criteria.md`. You get three pairs: features and use cases, use cases and acceptance criteria, features and acceptance criteria.
2. If you did 4B, you already have a reviewer. Here you can reuse the same kind of read-only helper. Ask:
   > "Run three subagents in parallel, all read-only. Subagent 1 compares features.md with use-cases.md. Subagent 2 compares use-cases.md with acceptance-criteria.md. Subagent 3 compares features.md with acceptance-criteria.md. All files are in data/corvane/s4/requirements-pack/. Each looks only for statements that contradict each other (different numbers, different people, different formats). Each returns a short list: what the two files say, file name and line number."
3. Watch the agent start the three at once. Notice that your main chat is not filled with their reading: you only get three short reports back.
4. Ask the main agent to merge:
   > "Merge the three reports into workspace/work/consistency-report.md. List each contradiction once, with both statements, file names and line numbers, and a suggested question to ask the business. Remove duplicates."
5. Check one contradiction yourself: open both files at the given lines and read them side by side.

## Definition of Done

- `workspace/work/consistency-report.md` exists.
- It lists exactly the three contradictions in Mentor reference, each with both file names and line numbers.
- You can explain why the three checks could run at the same time.

## Hints (mentor: one at a time)

1. If the agent ran the checks one after another, ask: "Did you start all three at the same time? Say 'run them in parallel' explicitly."
2. If a line number is wrong, tell the learner to open the file and count, then ask the agent to recheck that one.
3. If the report has more than three items, ask for the evidence for each extra one: "Show me the two lines that disagree."

## What you just learned

Independent checks can run side by side, each in its own room, and a final step merges the reports. You kept your own chat free for judgment instead of reading.

**Bring it to your job:** the next time you have three or more documents that must agree (a contract, a plan, a price list), ask for pair-by-pair checks in parallel.

## Mentor reference

Exactly three contradictions in `data/corvane/s4/requirements-pack/`:

1. **Tolerance value:** `features.md` line 5 (F-2): below 1% of the line value. `acceptance-criteria.md` lines 8-9 (AC-2): below 50 PLN. The 1% rule is the current one (21 Oct follow-up). Pair: features and acceptance criteria.
2. **Who approves a dispute:** `features.md` line 11 (F-5): the reconciliation lead. `use-cases.md` lines 10-11 (UC-2): the buyer. Pair: features and use cases.
3. **Export format:** `use-cases.md` line 20 (UC-4): CSV. `acceptance-criteria.md` line 18 (AC-5): XLSX. (`features.md` line 15, F-7, also says CSV.) Pair: use cases and acceptance criteria.

Common misses: reporting UC-3 versus AC-2 as a contradiction (it is not). Accept the contradiction pairs in any wording as long as file and line match.
