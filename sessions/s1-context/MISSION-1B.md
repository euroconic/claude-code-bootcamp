# Mission 1B - Merge Five Messy Regional Files

> Mentor: stretch mission, same loop as 1A on messier data. The point is a rule that surprises people: when two records conflict, the agent must not pick one. Watch for the agent quietly choosing the higher credit limit "to be helpful". If it does, send the learner back to the rules in `load-format.md`.

## Goal

Merge five regional customer-update files into one clean load file that follows `data/corvane/s1/load-format.md`, and write down every problem you found in an exceptions file.

## Why it matters

Corvane's five regional offices each send customer master updates in their own Excel layout. Someone has to merge them by hand before the ERP can import them. The files use different column names, different date styles, and different number formats, and a few rows are wrong. This is the most common office chore in the world, and the dangerous part is not the typing: it is the quiet decisions. If two offices disagree about a customer's credit limit, a person should decide, not a script.

## What to do

1. Read `data/corvane/s1/load-format.md`. Those are the target columns and the rules.
2. Open two of the five files in `data/corvane/s1/regional-exports/` and compare. Notice that the same information has different column names and different date styles.
3. Switch to plan mode (Shift+Tab). Ask for a plan, not a result:
   > "Read the five Excel files in data/corvane/s1/regional-exports/ and the rules in data/corvane/s1/load-format.md. I want a merged CSV at workspace/work/customer-load.csv and an exceptions file at workspace/work/merge-exceptions.md. Do not create anything yet. First inspect the files and tell me: how each file's columns map to the target columns, what date and number formats you found, and any rows that look wrong. Then give me your plan."
4. Read the plan and the list of problems the agent found. Does it mention the blank row, the duplicates, the missing tax ID, and the decimal commas? Add anything it missed. Approve the plan.
5. Let it build. Open `customer-load.csv` and `merge-exceptions.md`.
6. **Check against the source.** Verify, with the agent and by looking at the originals:
   > "Count the data rows in each of the five source files. Then show a table: total rows read, blank rows dropped, exact duplicates dropped, rows moved to exceptions, rows in the load file. The numbers must add up."
7. Spot-check three rows yourself: one from a file with a decimal comma, one from the file with month/day dates, and the row with the missing tax ID. Is the credit limit a plain number with a dot? Is the date YYYY-MM-DD?
8. Open the exceptions file. Is the conflicting customer there with both versions and the file each came from? If the agent chose one version, tell it the rule and ask it to redo the merge.

## Definition of Done

- `workspace/work/customer-load.csv` has the 8 target columns in the right order, dates as YYYY-MM-DD, credit limits as plain numbers with a dot.
- `workspace/work/merge-exceptions.md` lists the conflicting customer (both versions, with source files) and the row with the missing tax ID.
- The numbers add up: rows read, dropped, excepted, loaded.
- You spot-checked three rows against the original files.

## Hints (mentor: one at a time)

1. If the agent merges everything into one table without looking at the headers first, ask: "Did you compare the column names of all five files before merging?"
2. If the load file contains the same customer twice, ask the agent to list every customer_id that appears more than once, and to say for each whether the two rows are identical or different.
3. If a date looks wrong, remind them that the east file writes month first, as in 10/09/2026 meaning 9 October. Ask the agent how it decided which part is the month.

## What you just learned

You gave the agent a rulebook (`load-format.md`) and it followed it, including the rule "do not choose", which is the hard one. You also made it count: a merge is only trustworthy when rows read minus rows dropped minus rows excepted equals rows loaded.

**Bring it to your job:** the next time you combine exports from several people or systems, write the rules into a short file first, and ask for a row-count reconciliation at the end.

## Mentor reference

Expected results.

| Item | Count |
|---|---|
| Data rows in the five files (header rows excluded) | 51 (includes 1 fully blank row) |
| Blank rows dropped | 1 (east file) |
| Exact duplicates dropped | 1 (customer C-1003, Baltyk Catering, in both north and central; keep one) |
| Conflicting duplicates moved to exceptions | 1 customer, 2 rows: C-3005 Dom Kultury Zachod, credit limit 30,000 in the south file, 45,000 in the west file |
| Rows in `customer-load.csv` | 47 (47 unique customers) |
| Missing tax ID, kept in the load and flagged in exceptions | 1: C-4004 Akademia Tanca (west file) |

Check: 51 read - 1 blank - 1 duplicate - 2 conflicting = 47 loaded.

Other things a strict reviewer should see:
- Decimal-comma credit limits (south and west files) converted to dots, for example 8000,75 becomes 8000.75.
- East dates are month/day/year; south and central are day.month.year; north and west are already ISO. Every `valid_from` is YYYY-MM-DD.
- `source_file` filled for every row.
- The conflicting customer appears in neither the load file nor as a chosen version anywhere: both values are listed in exceptions, no recommendation presented as a decision.

**Common misses to push back on:** keeping the higher credit limit; dropping the missing-tax-ID row instead of keeping and flagging it; treating C-1003 as a conflict (the two rows are identical); mis-reading east dates as day first.
