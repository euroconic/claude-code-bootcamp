# Mission 5C - Cost, Tokens, and Rollback

> Mentor: stretch mission of session 5, and the answer to "what does this cost, and what if the agent breaks something?". Two halves: cost (understand it, measure your own usage, compare two ways of paying) and rollback (break a file on purpose, then undo it). Do NOT quote prices or plan names with numbers yourself: prices change, and the learner must look up the vendor's official pricing page and write down the page and the date. Check that a source and a date are written. If 4A or git is not set up yet, set it up first with the learner (Mission 09 shows the steps).

## Goal

Understand what an agent costs and why, see your own usage number, compare two ways to pay for a Corvane scenario using prices you looked up yourself, learn three habits that save tokens, and practice undoing a bad change. Output: `workspace/work/cost-and-rollback.md`.

## Why it matters

Two questions come up the moment a team wants to use an agent for real: "What will this cost us?" and "What if it breaks something?" The honest answer to the first is "it depends on how much text the agent reads and writes", and you can measure that. The honest answer to the second is "you undo it", and the only way to feel safe is to have done it once.

Plain words:

- **Token:** a small piece of a word (a short word is one token, a long word may be two or three). The agent is charged for every token it reads and every token it writes. That includes the files it opens, not only what you type.
- **Subscription:** a fixed monthly fee for personal use, with a usage limit that resets.
- **Pay-per-use (API):** no monthly fee; you pay for the tokens a program uses. Normal for programs that run by themselves, like a nightly report.
- **Rollback:** putting a file back to an earlier saved state.

## What to do

**Part A. Tokens, and your own number**

1. Ask the agent to explain tokens with one Corvane example:
   > "Explain tokens in plain words for a non-coder. Use one example: how many tokens might it take to read the Norden Clean invoice and write a three-line summary? Say clearly that this is a rough guess."
2. Look at your own usage in the tool. Type `/context` to see what fills the agent's working memory right now, and `/cost` to see usage for this session. If `/cost` shows no money because your plan is a subscription, use the token numbers it shows. Write down the number and what it counts (this session, in tokens). Do not worry if it looks big.

**Part B. Two ways to pay**

3. Look up current prices yourself, on the vendor's official pricing page (open it in your browser and search for the vendor's name plus "pricing"). Do not take prices from the agent or from memory. Write down: the page address, the date you looked, the subscription price per person per month, and the price per million tokens for pay-per-use.
4. Compare two Corvane scenarios using the numbers you wrote down:
   - **Scenario 1:** five people from the working group use the agent every working day.
   - **Scenario 2:** one nightly automated report: a program runs once a night, reads the day's purchase-order export, and writes a short summary.
   > "Here are the prices I looked up, with source and date: [paste your notes]. Help me compare scenario 1 and scenario 2. Ask me for every number you need (how long a typical session is, how many files the report reads) and show the calculation. Mark every estimate as an estimate."
5. Write one line: which way fits which scenario, and what you are unsure about.

**Part C. Three habits that save tokens**

6. Ask the agent to show each habit on a small example, then write them in your own words:
   > "Show me three habits that save tokens, each with a before and after example from the Corvane work: 1) point to a file instead of pasting its contents, 2) start a fresh session for a new task, 3) keep the memory file short. Explain why each one saves tokens."

**Part D. Rollback**

7. Make sure there is something to roll back. You need `workspace/work/prototype/index.html` from Mission 4A and git set up (Mission 09). If not, do those first. Then ask:
   > "Show me git status. Make sure workspace/work/prototype/ is committed, and commit it with a clear message if it is not. Then tell me the exact commands you would use to undo a bad change to index.html, and what they would throw away."
8. Open `workspace/work/prototype/index.html` in your browser so you know what a good page looks like.
9. Break it on purpose:
   > "Make one deliberate break in workspace/work/prototype/index.html, something that makes the page look clearly wrong when I open it (for example delete the page's styling block or the main button's code). Tell me exactly what you changed. Do not commit it."
10. Open the page again and see it broken. Ask the agent to show what changed since the last save point (`git diff`) and read it with you.
11. Undo it. Two ways: the git way (`git restore workspace/work/prototype/index.html`, which puts the file back to the last commit), or the tool's own undo (type `/rewind` and pick the checkpoint before the break). Use the git way at least once.
    > "Undo the deliberate break in workspace/work/prototype/index.html. Show me the command, then show me that git status is clean."
12. Open the page again and confirm it works. Note the rule: undoing only brings back what was saved before. If you had not committed, the good version would be gone. Commit early, break safely.
13. Write the note:
    > "Create workspace/work/cost-and-rollback.md with four sections: 1) my usage number from the tool and what it counts; 2) cost comparison for the two scenarios, with the pricing page address and the date I looked, and the calculation; 3) my three token-saving habits; 4) the rollback steps I actually ran, with the commands and what I saw. Do not add any price I did not give you."

## Definition of Done

`workspace/work/cost-and-rollback.md` exists and:

- States the learner's own usage number from the tool and what it measures.
- Explains tokens in the learner's own words, including that files the agent opens count.
- Compares both scenarios with the pricing page address, the date, the prices the learner looked up, and a calculation marked as an estimate.
- Lists three token-saving habits (point to a file, fresh session per task, short memory file).
- Lists the rollback steps the learner actually ran, and the learner can say what `git restore` throws away.

`workspace/work/prototype/index.html` is back in its good state, with a clean `git status`.

## Hints (mentor: one at a time)

1. Learner asks "how much does it cost?" Say: that is the point of this mission. Open the vendor's pricing page together and let the learner read the current numbers.
2. Learner cannot find the usage number? Try `/context` first, then `/cost`. If neither works in their setup, they write the token figure from `/context` or say what they saw.
3. Rollback feels scary? Say: the break is in one file you can always rebuild. The commit is your safety net. Confirm `git status` shows the file as committed before the break.

## What you just learned

An agent's cost follows what it reads and writes, so you can measure it and lower it with a few habits. Prices change, so you write down the source and date instead of memorizing numbers. And a mistake is cheap when you have a save point: you broke a file on purpose and put it back.

**Bring it to your job:** before you pilot a chore, write one line: "I expect it to read about X files a day" and check the usage number after a week.

## Mentor reference

Do not accept any price without a source and date. Accept the note when:

- A usage number from the tool is written with what it counts. Any number is fine.
- Both scenarios are compared with calculations and a stated source (the vendor's official pricing page) and a date. The mentor does not judge the price values, only that they come from a named page and are dated.
- The expected reasoning: scenario 1 (five people, interactive, daily) usually fits a subscription per person, because usage is hard to predict and spread across people; scenario 2 (one program, one report a night, a small predictable amount of text) usually fits pay-per-use, because it is small and measurable. Accept the opposite if the learner's own numbers support it.
- The three habits: point to a file instead of pasting its contents; start a fresh session for a new task (old text keeps being re-read and paid for); keep the memory file short (it is read at the start of every session).
- Rollback steps: the file was committed first; the break was made; the learner saw it broken; `git restore <file>` (or `/rewind`) brought it back; the page works again. The learner can say that `git restore` discards unsaved changes to that file for good.

If any of these is missing, name the single most important gap first. An invented or unsourced price comes first.
