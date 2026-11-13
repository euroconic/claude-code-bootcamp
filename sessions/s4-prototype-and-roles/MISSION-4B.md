# Mission 4B - A Reviewer Who Can Only Read

> Mentor: stretch mission. The point is the idea of a role: one job, limited access, own room. Let the learner decide what the reviewer must not be allowed to do before they write the file. Resist explaining all the planted problems; the reviewer should find them.

## Goal

Create a subagent called `brd-reviewer` that reads a BRD and reports problems, and cannot change any file. Run it on `data/corvane/s4/brd-draft-with-issues.md` and save its report to `workspace/work/brd-review.md`.

## Why it matters

Reviewing a long document is tiring and you stop seeing your own mistakes. A reviewer colleague with fresh eyes catches what you miss. And a reviewer who can only read is safe: it cannot "fix" things on its own or overwrite your work.

A **subagent** is a colleague with one job and limited access. It works in its own room (its own separate conversation), reads what you point it to, and returns a short report. Your main chat stays clean. A **skill** is different: it is a recipe the main agent follows. A skill says how; a subagent is someone who does it.

## What to do

1. Open `data/corvane/s4/brd-draft-with-issues.md` and read it yourself for two minutes. Write down any problems you notice. Do not look at the answer yet.
2. Ask your agent to create the colleague:
   > "Create a subagent in .claude/agents/brd-reviewer.md. Its job: review a business requirements document. It may only use the tools Read, Grep and Glob, so it can look but never change files. It checks that every requirement (1) can be traced to something said in a call or document, (2) has an acceptance criterion, (3) does not contradict another requirement, (4) contains no vague words like fast, easy or soon without a number. It returns a short report: issue, where (BR number and line), why it is a problem, a suggested fix."
3. Open the new file. Check the top part (between the two lines of `---`): it should have a `name`, a `description` and `tools: Read, Grep, Glob`. The tools line is the lock on the door: Read opens files, Grep searches inside them, Glob finds files by name. There is no tool for writing, so the reviewer cannot edit anything.
4. Run it:
   > "Use the brd-reviewer subagent on data/corvane/s4/brd-draft-with-issues.md. The call transcripts are in data/corvane/s2/. Save its report as workspace/work/brd-review.md."
   (The reviewer cannot write files; the main agent saves the report. That is the point.)
5. Compare the report with your own notes from step 1. What did the reviewer find that you missed? What did it flag that is not really a problem?

## Definition of Done

- `.claude/agents/brd-reviewer.md` exists with `name`, `description` and `tools: Read, Grep, Glob` (nothing else).
- `workspace/work/brd-review.md` exists and contains the four issues listed in Mentor reference, each with the BR number and a suggested fix.
- You can say in one sentence why the reviewer is read-only.

## Hints (mentor: one at a time)

1. If the learner gave the reviewer all tools, ask: "What could go wrong if the reviewer could also write files?"
2. If the report misses the invented requirement, ask the agent: "Which requirement has no matching passage in the two call transcripts? Search for the word email."
3. If the report is long and vague, say: "Ask for one line per issue: BR number, problem, fix."

## What you just learned

You hired a colleague with one job and a locked toolbox. It worked in its own room and returned a short report, and your main chat stayed clean. Limiting what a helper can do is how you trust it.

**Bring it to your job:** create a read-only reviewer for the document type you review most often (contracts, specs, reports) and run it before you send anything out.

## Mentor reference

File: `data/corvane/s4/brd-draft-with-issues.md`. Exactly four planted issues:

1. **Not traceable (invented requirement):** BR-4, lines 31-33. The automatic email to suppliers appears in neither call. Fix: remove it or move it to Open questions.
2. **No acceptance criterion:** BR-7, lines 43-44. The comment trail has no acceptance criteria. Fix: add a testable criterion.
3. **Contradiction:** BR-5 (lines 35-37) says only reconciliation can close a discrepancy; BR-6 (lines 39-41) says only the buyer can. The calls left this open (14 Oct, 05:18). Fix: one rule, or move to Open questions until the purchasing head decides.
4. **Vague word:** BR-3, lines 27-29: "fast". Fix: a measurable target (for example, the list is shown within 5 seconds of loading a file).

Not issues (do not count as findings): BR-2 uses 1% of line value, which is correct per the 21 Oct follow-up. The subagent file must have `tools: Read, Grep, Glob`; a version with Write or Edit fails the mission.
