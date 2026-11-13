# Mission 4A - BRD to Clickable Prototype

> Mentor: this is the core mission of session 4. The win is that the learner sees their written requirements become something they can click, and learns that changing it is as easy as writing a comment. Make them start with a plan, and make them open the file in a browser themselves. Do not let them accept the first version without clicking every control.

## Goal

Turn the BRD into a single-page prototype at `workspace/work/prototype/index.html` that opens in a browser: a list of discrepancies (supplier, invoice, line, type, amount at risk), a filter by supplier, a status you can change (Open, Accepted, Disputed), and a comment box. Then improve it with two rounds of plain-language comments.

## Why it matters

People rarely agree on a document, but they quickly agree on a screen. A prototype exposes missing details in minutes: "wait, where do I see the invoice number?" It is also the cheapest way to show Marta's team what they will get before anyone writes real software.

A **prototype** is a model of the tool that looks and clicks like the real one but holds no real data connections. Think of the cardboard model of a building: you can walk around it, but nobody lives in it.

## What to do

1. Pick your input. Use your own BRD from mission 2C if you have it at `workspace/work/brd-discrepancy-tool.md`. If not, use `data/corvane/s4/brd-discrepancy-tool-reference.md`.
2. Ask for a plan first, without building. In Claude Code, press Shift+Tab until the mode says "plan mode" (the agent may then only think and propose, not change files). Then say:
   > "Read the BRD at data/corvane/s4/brd-discrepancy-tool-reference.md and the discrepancy check from session 1 at workspace/work/invoices.xlsx. Propose a plan for a single-file HTML prototype: which columns, which filter, which statuses, where the comment box goes. Do not write any files yet."
3. Read the plan. Is every requirement from the BRD visible on screen? Ask one question about something missing, then approve the plan (leave plan mode with Shift+Tab).
4. Build it:
   > "Build the prototype as one file, workspace/work/prototype/index.html. No server, no internet needed. Show the discrepancies from the session 1 check: supplier, invoice number, line, type (price or quantity), amount at risk with currency. Add a filter by supplier, a status per row that I can change between Open, Accepted and Disputed, and a comment box per row. If the session 1 workbook is missing, use the two mismatches listed in the BRD."
5. Open the file in your browser (double-click it in your file manager, or ask the agent to run `open workspace/work/prototype/index.html`). Click every control. Change a status, filter by supplier, type a comment.
6. Round one of edits, by plain comment:
   > "Make the amount column right-aligned and show it with 2 decimals."
7. Round two:
   > "Add a total at risk at the top, one total per currency, that updates when I filter."
8. Reload the page in the browser after each round and check the change with your own eyes.

## Definition of Done

- `workspace/work/prototype/index.html` exists and opens in a browser with no server.
- It shows the discrepancy rows with all five columns, a supplier filter, a three-value status and a comment box.
- The amount column is right-aligned with 2 decimals, and a total at risk is shown per currency (see Mentor reference).
- You made at least two rounds of edits using plain comments.

## Hints (mentor: one at a time)

1. If nothing appears when opening the file, ask the learner to describe what they see: blank page, or an error? Then ask the agent: "The page is blank. Find out why and fix it."
2. If the rows are invented instead of taken from the check, ask: "Where did these numbers come from? Compare them with the BRD."
3. If the filter works but the total does not update, point at the screen, not the code: "When I pick Norden Clean, what should the total say? Tell the agent that sentence."

## What you just learned

A written requirement became a clickable screen in minutes, and each improvement was a single sentence. Planning first kept the agent from guessing, and opening the file yourself is the check: the browser does not lie.

**Bring it to your job:** take the next requirement or idea you would normally describe in a document, and ask for a one-file clickable prototype before you write the full text.

## Mentor reference

Expected content. Layout may differ; the facts must match.

**Rows (2 discrepancies):**

| Supplier | Invoice | Line | Type | Amount at risk |
|---|---|---|---|---|
| Baltic Pack | BP-44120 | Carton box 400x300x300 | Price (2.35 vs 2.15 agreed, 1,000 units) | 200.00 PLN |
| Norden Clean | NC-2026-0912 | Dish detergent 5L | Quantity (150 vs 120 ordered) | 217.50 EUR |

**Checks:**
- Supplier filter: choosing Baltic Pack shows one row; Norden Clean shows one row; "All" shows two.
- Status: starts as Open; can be set to Accepted or Disputed; a reload may reset it (no storage required).
- Comment box per row accepts text and shows it.
- Round 1: the amount column is right-aligned, with values such as 200.00 and 217.50.
- Round 2: total at risk is shown per currency, never summed across currencies: 200.00 PLN and 217.50 EUR. With a supplier filter, only that supplier's total shows.
- Single file, no external server calls needed to work.
- Common misses: adding PLN and EUR into one number; Quantity row showing a unit price difference instead of 30 extra units; invented rows.
