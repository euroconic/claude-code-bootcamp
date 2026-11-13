# Use cases: Supplier Discrepancy Tool

## UC-1. Review today's discrepancies
Actor: reconciliation analyst.
Steps: open the shared screen; filter by supplier; open a discrepancy; read the invoice and PO values side by side.
Result: the analyst knows which lines need action.

## UC-2. Dispute a discrepancy
Actor: reconciliation analyst, buyer.
Steps: the analyst sets the status to Disputed and adds a comment; the buyer approves the dispute; the buyer contacts the supplier.
Result: the supplier is contacted only after the buyer has approved.

## UC-3. Accept a small difference
Actor: system.
Steps: the system compares each line; a difference below the tolerance is accepted without a human step.
Result: the line does not appear in the list.

## UC-4. Export for the monthly report
Actor: Head of Supplier Reconciliation.
Steps: choose the month; press Export; the tool produces a CSV file with all discrepancies of the month.
Result: the file opens in Excel and is attached to the monthly report.
