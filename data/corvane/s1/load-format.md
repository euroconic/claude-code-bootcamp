# Customer load format

Corvane's ERP imports customer master updates from one CSV file with exactly these columns, in this order:

| Column | Format | Notes |
|---|---|---|
| customer_id | text, like C-1001 | one row per customer |
| name | text | |
| city | text | |
| tax_id | text | may be empty, see rules |
| credit_limit_pln | number with a dot as the decimal separator, like 12000.50 | no thousands separators, no currency sign |
| payment_terms_days | whole number | |
| valid_from | YYYY-MM-DD | |
| source_file | text | the regional file the row came from |

## Rules

1. Drop rows that are completely blank.
2. Drop exact duplicates: the same customer with identical values in every field. Keep one copy.
3. Never choose between conflicting duplicates. If one customer_id appears twice with different values (for example two different credit limits), leave both rows out of the load file and write both into the exceptions file so a person decides.
4. Keep rows with a missing tax ID in the load file, but list them in the exceptions file under a separate heading "Missing tax ID" so someone can fill them in.
5. Date notes: the east file writes dates as month/day/year. The south and central files write day.month.year. The north and west files already use YYYY-MM-DD.
6. Credit limits in some files use a decimal comma (12000,50). Convert them to a dot.
