# BRD DRAFT: Supplier Discrepancy Tool (v0.3, not yet reviewed)

Author: Irene Holt. Sources: the 14 October kickoff call and the 21 October follow-up call.

## 1. Background

Month-end checks of supplier invoices against purchase orders take about two and a half days of three people (14 Oct, 00:32). Overcharges of 14,000 PLN were found last quarter, after payment.

## 2. Goal

See price and quantity mismatches before payment, in one place.

## 3. Scope

In scope: Baltic Pack and Norden Clean for the first month (14 Oct, 02:00). Out of scope: other suppliers, ERP replacement.

## 4. Business requirements

**BR-1. Shared discrepancy list.**
One screen lists all price and quantity mismatches for the pilot suppliers (14 Oct, 02:51).
Acceptance criteria: with the sample data the list shows exactly two mismatches, each with supplier, invoice, line, type and amount at risk.

**BR-2. Tolerance.**
Differences under 1% of line value are auto-accepted (21 Oct, 03:21).
Acceptance criteria: a 23.00 PLN difference on a 2,350.00 PLN line is accepted; 24.00 PLN is listed.

**BR-3. Fast loading of invoices.**
The tool must load the invoices of the day fast, so that analysts can start work at once.
Acceptance criteria: invoices appear in the list after the file is loaded.

**BR-4. Automatic email to suppliers.**
When a discrepancy is marked Disputed, the tool automatically sends an email to the supplier with the details and a request for a credit note.
Acceptance criteria: the supplier receives the email within one hour.

**BR-5. Closing a discrepancy by the reconciliation team.**
Only a member of the reconciliation team can close a discrepancy, because they own the payment decision.
Acceptance criteria: a buyer who tries to close a discrepancy sees a message that only reconciliation can close it.

**BR-6. Closing a discrepancy by the buyer.**
The buyer who placed the order closes the discrepancy once the supplier has answered, because the buyer talks to the supplier.
Acceptance criteria: the discrepancy leaves the Open list when the buyer marks it closed; reconciliation staff cannot close it.

**BR-7. Comment trail.**
Users can add comments to a discrepancy and the comments stay with it.

**BR-8. Pilot scope.**
Only invoices from Baltic Pack and Norden Clean are processed (14 Oct, 02:00).
Acceptance criteria: an invoice from another supplier is reported as out of pilot scope.

## 5. Open questions

1. Can the ERP export PO lines automatically every day?
2. EUR conversion: invoice date or payment date?

## 6. Sources

14 Oct kickoff call, 21 Oct follow-up call.
