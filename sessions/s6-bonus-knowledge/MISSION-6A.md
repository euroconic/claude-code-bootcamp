# Mission 6A - Read-Only Policy Researcher

> Mentor: bonus mission, about 35 minutes. Do it after session 5. The lesson is trust: an answer without a source is a rumor, and a good researcher says "not in the sources" instead of guessing. Question 3 is the trap on purpose: there is no penalty policy. Do not give the answer away; let the learner see how the researcher handles it.

## Goal

Build a read-only helper called `policy-researcher`, make a map of which policy answers what, and use the helper to answer three questions with file citations.

## Why it matters

Company rules live in documents that nobody reads end to end. People ask the owner the same questions every week. A researcher that reads the policies for you, quotes the file and section, and admits when something is not written down can take hours off both sides. The risk is an agent that sounds sure and is wrong. The fix is a strict rule: answer only from the sources, and cite them.

A **read-only** agent can look at files and search them, but it cannot create, edit, or delete anything. It is like a librarian who finds the book but is not allowed to write in it.

## What to do

1. Skim the folder `data/corvane/s6/policies/`. Eight short files. Do not read them closely yet.
2. Make a source map:
   > "Read the 8 files in data/corvane/s6/policies/. Write workspace/work/source-map.md: a table with file name, owner, and 'answers questions about' (one line each). Do not add anything that is not in the files."
3. Create the read-only researcher:
   > "Create a subagent called policy-researcher in .claude/agents/policy-researcher.md. A subagent is a helper with its own job and its own list of allowed tools. Give it only these tools: Read, Grep, Glob. Its rules: answer only from files in data/corvane/s6/policies/; cite the file name and section number for every claim; if the answer is not in the files, say exactly 'Not found in the sources' and do not guess; never write or change files."
4. Open `.claude/agents/policy-researcher.md` with your mentor. Find the `tools:` line. It should list only Read, Grep, Glob. That line is what makes it read-only.
5. Ask the researcher three questions. Use the helper by name, one question at a time:
   > "Use policy-researcher: who approves a credit note above 5,000 PLN?"
   > "Use policy-researcher: in the October check, the Baltic Pack carton box line had a 200.00 PLN overcharge on a line value of 2,350.00 PLN. Is that within tolerance?"
   > "Use policy-researcher: what is the penalty for late supplier delivery?"
6. Save the answers yourself (the researcher cannot write files):
   > "Write the three questions and the researcher's answers to workspace/work/policy-answers.md. For each answer keep the file name and section. Do not change what the researcher said."
7. Check each citation yourself: open the cited file and find the section. It takes one minute and it is the habit that matters.

## Definition of Done

- `workspace/work/source-map.md` lists all 8 policy files with an owner and a topic.
- `.claude/agents/policy-researcher.md` exists and its `tools:` line contains only Read, Grep, Glob.
- `workspace/work/policy-answers.md` has three answers, each with a file and section citation, and question 3 says the answer is not in the sources.
- The learner opened at least one cited file and confirmed the quote.

## Hints (mentor: one at a time)

1. If the researcher answers from general knowledge without citations, ask the learner what rule in the helper file forbids that, and have them tighten it.
2. If question 1 returns two answers, ask: which of the two policies owns approval amounts, and does the other one only point to it?
3. If the researcher invents a penalty for question 3, show them: search the folder for the word "penalty". Nothing. Then make the "Not found in the sources" rule stronger and ask again.

## What you just learned

You gave an agent a library, restricted it to reading, and forced it to show its sources. You also saw the most important behavior of a trustworthy research helper: it says "not in the sources" instead of making something up.

**Bring it to your job:** collect 5 to 10 real documents from your own team (policies, procedures, FAQs), put them in one folder, and build the same read-only researcher for them.

## Mentor reference

Expected answers. Check each one against the quoted policy text.

1. **Who approves a credit note above 5,000 PLN?** The COO. Source: `05-approval-matrix.md`, section 2 (Credit notes): "5,000.01 to 50,000.00 PLN: COO". Above 50,000.00 PLN the COO and CFO approve together. Supporting: `04-credit-notes.md`, section 4 says the approver depends on the amount as in Policy 05. Not acceptable: "Head of Supplier Reconciliation" (that band ends at 5,000.00 PLN).

2. **Is the 200.00 PLN carton overcharge within tolerance?** No. Source: `03-discrepancy-tolerance.md`, section 2 (tolerance is 1% of line value, minimum 20.00 PLN, whichever is higher) and section 6 (example with a 2,350.00 PLN line). 1% of 2,350.00 = 23.50 PLN, which is higher than 20.00 PLN, so the tolerance is 23.50 PLN. 200.00 PLN is above it, so it is a discrepancy. Next step per section 5 point 2 and `04-credit-notes.md` section 1: the buyer requests a credit note or a corrected invoice. Not acceptable: the old flat 50 PLN limit (replaced in version 2.0).

3. **Penalty for late supplier delivery?** Not found in the sources. No policy in the folder defines late-delivery penalties. The correct answer says so and suggests asking the owner (Procurement or Operational Excellence) instead of guessing. Any specific percentage or amount is an invented answer.

Common misses: citing a file without the section; answering question 1 with the CFO only; learner skipping the check of the cited text; `tools:` line containing Write, Edit, or Bash.
