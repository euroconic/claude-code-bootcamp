# Mission 1A - Invoices to a Checked Spreadsheet

> Mentor: this is the core mission of session 1. The win is not the spreadsheet. The win is that the learner meets the loop plan, build, check, and sees the agent catch two real mistakes in supplier invoices that a person reading PDFs by eye would probably miss. Make them switch to plan mode before any file is created, and make them verify at least two numbers against the PDFs themselves. If they say "looks right", ask which number they opened.

## Goal

Read three supplier invoices (PDF), compare each line with the purchase order, and produce `workspace/work/invoices.xlsx` with a `Lines` sheet, a `Check` sheet, and two charts. Then prove that the totals match the PDFs.

## Why it matters

Marta's team at Corvane checks supplier invoices against purchase orders by eye, late in the month. Most lines are fine; a few are wrong, and each wrong line is real money. A chat window cannot open three PDFs and a CSV file from your disk, build a workbook, and save it. An agent can, but it can also make a quiet mistake. So you work in three steps: **plan** what it should do, let it **build**, then **check** the result against the source documents yourself.

A **purchase order** (PO) is the order Corvane sent to the supplier: what to deliver, how many, at what agreed price. The invoice is the supplier's bill. If the invoice says something different from the PO, somebody should ask why before paying.

## What to do

1. Look at what you have. Open one invoice PDF and `data/corvane/s1/po-export.csv`. Notice that the PO file lists the agreed quantity and agreed unit price for every line.
2. **Switch to plan mode.** In Claude Code, press Shift+Tab until the bottom of the screen says plan mode. In plan mode the agent can read your files and think, but it proposes a plan and waits for your approval before it changes anything. It is like asking a contractor for a written quote before they start work. Then say:
   > "Read the three invoice PDFs in data/corvane/s1/invoices/ and the purchase-order file data/corvane/s1/po-export.csv. I want a spreadsheet at workspace/work/invoices.xlsx with a sheet called Lines (one row per invoice line) and a sheet called Check (each line compared with the PO: quantity difference, price difference, amount at risk, status OK or MISMATCH), plus two charts: spend by supplier, and amount at risk. Do not create anything yet. Give me a plan first: the columns you will use, how you will compare, and how you will handle the euro invoice."
3. Read the plan. Ask yourself two things: does it keep PLN and EUR separate (you cannot add them without an exchange rate), and does it say how it will check its own work? If not, tell it. Then approve the plan.
4. Let the agent build the workbook. When it finishes, open `workspace/work/invoices.xlsx` in Excel.
5. **Check against the source.** Do not trust the agent's summary. Open the three PDFs yourself and compare:
   - For each invoice, does the sum of the lines in `Lines` equal the net total printed on the PDF?
   - Does the VAT and gross total on the PDF match what the workbook shows?
   Write down the three net totals you found.
6. Ask the agent to check itself too:
   > "Recalculate the net, VAT and gross total of each invoice from the Lines sheet and compare them with the totals printed on the PDFs. Tell me any difference, even one cent."
7. Look at the `Check` sheet. How many lines are marked MISMATCH? Open the PO file and the PDF for those lines and confirm the difference with your own eyes.
8. Ask for one improvement using plain words, for example "put the mismatches at the top" or "color the MISMATCH rows light red", and check that the totals did not change.

## Definition of Done

- `workspace/work/invoices.xlsx` exists with sheets `Lines` and `Check` and two charts.
- `Lines` has 9 rows (3 per invoice). `Check` marks exactly the lines that differ from the PO.
- PLN and EUR amounts are never added together.
- You compared the invoice totals with the PDFs yourself and they match.

## Hints (mentor: one at a time)

1. If the agent returns a single "total spend" number, ask: "Two of these invoices are in zloty and one is in euro. Can we add them?"
2. If a PDF cannot be read, ask the agent which tool it used and whether it can extract the text from the PDF first, then build the table from that text.
3. If the learner says the totals match but cannot name them, send them back to step 5. The Mentor reference below lists the numbers; do not show it before they have tried.

## What you just learned

An agent works on your files, not on text you pasted. You asked for a plan before any file was created, so you could steer it cheaply. After the build, you did not accept "done": you opened the source documents and compared. That last step is what separates using an agent from trusting one.

**Bring it to your job:** take one weekly pile of documents you currently check by eye (invoices, orders, timesheets), ask for a plan first, and compare the result against two of the originals before you rely on it.

## Mentor reference

Expected results. Wording and layout may differ; the numbers must match.

**Invoice totals:**

| Invoice | Supplier | Currency | Net | VAT | Gross |
|---|---|---|---|---|---|
| VP-2026-1187 (2026-10-03) | Vistula Paper | PLN | 6,098.00 | 1,402.54 (23%) | 7,500.54 |
| BP-44120 (2026-10-07) | Baltic Pack | PLN | 6,226.00 | 1,431.98 (23%) | 7,657.98 |
| NC-2026-0912 (2026-10-09) | Norden Clean GmbH | EUR | 3,179.50 | 0.00 (reverse charge) | 3,179.50 |

**Lines:** 9 in total. **Mismatches:** 2.

| Invoice | Line | Difference | Amount at risk |
|---|---|---|---|
| BP-44120 | Carton box 400x300x300 | invoiced 2.35, PO agreed 2.15, price +0.20 x 1,000 units | 200.00 PLN (net) |
| NC-2026-0912 | Dish detergent 5L | invoiced 150, PO ordered 120, 30 extra units x 7.25 | 217.50 EUR |

The other 7 lines are OK. Amount at risk is 200.00 PLN and 217.50 EUR, shown separately.

**Charts:** spend by supplier per currency (Vistula 6,098.00 PLN, Baltic Pack 6,226.00 PLN, Norden Clean 3,179.50 EUR), and amount at risk (two bars or two figures, one per currency).

**Common misses to push back on:** adding PLN and EUR into one total; reading gross instead of net as the amount at risk; marking the Norden VAT as 23% when the invoice says reverse charge (VAT 0); a Check sheet that shows differences but no status column; "totals match" without the learner having opened a PDF.
