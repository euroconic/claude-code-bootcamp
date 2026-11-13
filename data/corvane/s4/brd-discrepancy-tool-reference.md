# BRD: Supplier Discrepancy Tool (clean reference version)

Author: Irene Holt, Senior Business Analyst. Sponsor: Marta Kowal. Change request owner: Tomasz Wren.
Sources: the 14 October kickoff call (cited as 14 Oct, with timestamp) and the 21 October follow-up call (cited as 21 Oct, with timestamp).

## 1. Background

Every month-end the supplier reconciliation team checks supplier invoices against purchase orders by hand. It takes about two and a half days of three people (14 Oct, 00:32). Last quarter the team found 14,000 PLN of overcharges, but only after paying (14 Oct, 00:32). Mismatches live in emails and several spreadsheets (14 Oct, 01:30).

## 2. Goal and success metric

Goal: see price and quantity mismatches before payment, in one place.
Success metric: mismatches for the pilot suppliers are visible before the payment date (14 Oct, 01:30). A numeric target for time saved was not set on the calls and is listed under Open questions.

## 3. Scope

In scope:
- Pilot with two suppliers only, for the first month: Baltic Pack and Norden Clean (14 Oct, 02:00).
- Price and quantity mismatches between invoice lines and purchase-order lines.
- One shared discrepancy screen for the team and the buyers (14 Oct, 02:51).

Out of scope:
- Any other supplier during the pilot (14 Oct, 02:00).
- Replacing the ERP (14 Oct, 01:44).
- Retiring the existing Excel file: it stays as backup during the pilot (14 Oct, 03:04).

## 4. Users

- Reconciliation analysts (Marta's team): review and resolve discrepancies.
- Buyers: see discrepancies for their orders and talk to the supplier (14 Oct, 05:10).

## 5. Business requirements

**BR-1. Show discrepancies on one screen.**
The tool lists every price or quantity mismatch for the pilot suppliers in one shared list (14 Oct, 02:51).
Acceptance criteria: for the sample data of three invoices and nine PO lines, the list shows exactly the two mismatches (Baltic Pack carton box price, Norden Clean dish detergent quantity). Each row shows supplier, invoice number, line, type and amount at risk.

**BR-2. Compare invoice lines with purchase-order lines.**
Each invoice line is compared with its PO line on quantity and unit price (14 Oct, 00:57).
Acceptance criteria: a line with the same quantity and price as the PO never appears in the list; a line that differs always appears unless BR-3 applies.

**BR-3. Tolerance rule.**
A difference smaller than 1% of the line value is accepted automatically. This replaces the earlier rule of 50 PLN per line (14 Oct, 02:31), which was changed on the 21 Oct follow-up (21 Oct, 03:21).
Acceptance criteria: a line of 2,350.00 PLN with a difference of 23.00 PLN is auto-accepted; with a difference of 24.00 PLN it appears in the list.

**BR-4. Pilot scope.**
Only invoices from Baltic Pack and Norden Clean are processed in the first month (14 Oct, 02:00).
Acceptance criteria: an invoice from any other supplier is not loaded and is reported as out of pilot scope.

**BR-5. Status of a discrepancy.**
Each discrepancy has a status: Open, Accepted or Disputed (14 Oct, 05:10).
Acceptance criteria: a new discrepancy is Open; a user can change the status; the change is visible to all users of the screen at once.

**BR-6. Comment trail.**
Users can add comments to a discrepancy and the comments stay with it (14 Oct, 02:51: no more emails with attachments).
Acceptance criteria: a comment shows the author and the date and cannot be edited by others.

**BR-7. Mismatches visible before payment.**
Discrepancies are available before the supplier invoice is paid (14 Oct, 01:30).
Acceptance criteria: for each invoice in the pilot, the list is complete before its payment date. Whether payments can be held is still open (see Open questions).

## 6. Business rules

- Amounts are shown with 2 decimals.
- Tolerance is checked per line, not per invoice (14 Oct, 02:36), at 1% of line value (21 Oct, 03:21).
- No capacity for testing in the last week of each month (14 Oct, 06:05).

## 7. Open questions

1. Can the ERP export purchase-order lines automatically every day? (14 Oct, 04:05; IT question)
2. Who closes a discrepancy: the reconciliation team or the buyer? (14 Oct, 05:18; needs the purchasing head)
3. Are EUR invoices converted at the invoice-date or the payment-date rate? (14 Oct, 05:33)
4. Can finance hold a payment when a mismatch is found? (14 Oct, 04:29; owner Marta)
5. What time-saving target counts as success? (not discussed)

## 8. Sources

- 14 Oct kickoff call: data/corvane/s2/2026-10-14_reconciliation-kickoff.txt
- 21 Oct follow-up call: data/corvane/s2/2026-10-21_reconciliation-followup.txt
