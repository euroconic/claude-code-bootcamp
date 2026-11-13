# Acceptance criteria: Supplier Discrepancy Tool

## AC-1. Comparison
Given an invoice line and its PO line with the same quantity and price, the line does not appear in the list.
Given a line that differs, it appears with supplier, invoice, line, type and amount at risk.

## AC-2. Tolerance
Given a line with a difference below 50 PLN, the difference is accepted automatically.
Given a line with a difference of 50 PLN or more, it appears in the list.

## AC-3. Shared screen
Given two users on the screen, a status change by one is visible to the other without reloading.

## AC-4. Comments
Given a comment is added, it shows the author and the date and stays with the discrepancy.

## AC-5. Export
Given the user presses Export, the tool produces an XLSX file with one row per discrepancy and the columns supplier, invoice, line, type, amount at risk, status.
