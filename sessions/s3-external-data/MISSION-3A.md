# Mission 3A - Exchange-Rate Skill and Spend Report

> Mentor: this is the core mission of session 3. The learner builds a small skill that fetches a real exchange rate from a public website, then uses it in a report. Two things matter: the rate is fetched, not guessed (agents love to "remember" a rate), and the report shows where each number came from. Do not ship the skill. Build `fx-rate` together, step by step. The NBP service was checked and works without any key (see Mentor reference).

## Goal

Convert the Norden Clean invoice from EUR to PLN at the official National Bank of Poland (NBP) rate for the invoice date, using a skill called `fx-rate`. Then build `workspace/work/spend-report.html`: total spend per supplier in PLN, a bar chart, and a source line.

## Why it matters

Corvane buys in two currencies, so nobody can add up spend without a rate. Today someone opens the NBP site, copies a number, and pastes it into Excel. Months later nobody remembers which rate or which day. A skill that fetches the rate and prints the table number and date next to it makes the answer repeatable and checkable.

Three words, in plain terms:

- **API**: a delivery door. A website lets programs ask for data in a fixed format. NBP's door is public: no password.
- **MCP**: a service counter built for agents. You connect a tool once and the agent can ask it things. Good when many questions go to the same tool. Often needs a token (a program's password) and IT approval.
- **Script**: a few lines of instructions a computer runs. You will not write it. The agent writes it, you read what it does in plain words, and the skill stores it.

For a single public number, a skill with a small script is the simplest of the three. No account, no token.

## What to do

You can do this mission even if you skipped Session 1: the invoices are PDFs you can read directly.

1. Ask the mentor to explain the three ways in a minute, with a real example for each. You do not need to set up any MCP connection today.
2. Look at the invoices:
   > "Read the three invoices in data/corvane/s1/invoices/: 2026-10-03_vistula-paper_VP-2026-1187.pdf, 2026-10-07_baltic-pack_BP-44120.pdf and 2026-10-09_norden-clean_NC-2026-0912.pdf. For each, tell me the supplier, invoice date, currency and net total. Do not calculate anything yet."
3. Check the plan before building. Ask:
   > "I want the exchange rate for the Norden invoice date from the NBP website (api.nbp.pl, table A, euro). Explain in plain words how you would fetch it, what happens on a day with no published rate, and what could go wrong. Do not write anything yet."
4. Fetch one rate by hand first, so you know what a correct answer looks like:
   > "Fetch https://api.nbp.pl/api/exchangerates/rates/a/eur/2026-10-09/?format=json and show me the raw answer. Point out the rate, the date, and the table number."
5. Test the missing-day case. NBP publishes no rate on weekends and public holidays, and the website answers with a "404 Not Found" message (it means "no data for that day", not that the site is broken):
   > "Fetch the same address for 2026-10-10. What happens? Then show me how you would find the rate for the last day before it that has one."
6. Now build the skill:
   > "Create a skill called fx-rate in .claude/skills/fx-rate/SKILL.md, with a small script next to it. Input: a currency code and a date. It asks the NBP API for that day. If the answer is 404, it steps back one day at a time (at most 10 days) until it finds a rate. It prints the rate, the date the rate is actually from, and the table number. It never guesses a rate. If nothing is found, it says so."
7. Read the skill with your mentor. Ask: "Where would it go wrong if NBP's website were down?" Add a rule so it stops and tells you instead of inventing a number.
8. Use it:
   > "Use the fx-rate skill to get the EUR rate for 2026-10-09. Convert the Norden Clean invoice net total to PLN, rounded to 2 decimals. Show the calculation."
9. Build the report:
   > "Create workspace/work/spend-report.html, a single file I can open in a browser. Show total net spend per supplier in PLN (Vistula Paper, Baltic Pack, Norden Clean), a bar chart, and a table. Under it, add a source line: the EUR/PLN rate, the NBP table number, the rate date, and which invoice it was applied to. Use only numbers from the invoices."
10. Check it yourself: open the file in your browser. Do the three supplier totals match the PDFs? Is the source line there?
11. Ask the agent to challenge itself:
    > "Re-read the three PDFs and the fx-rate output. Does every number in spend-report.html match? List anything you are not sure about."

## Definition of Done

- `.claude/skills/fx-rate/SKILL.md` exists with a name, a description, a script, the 404 step-back rule, and a "never invent a rate" rule.
- The skill was run for 2026-10-09 and returned a real rate with a table number.
- `workspace/work/spend-report.html` opens in a browser and shows three suppliers in PLN, a bar chart, and a source line (rate, table number, date).
- Numbers match the Mentor reference below.

## Hints (mentor: one at a time)

1. If the agent offers to "use the usual rate", stop it: "Fetch it. Show me the raw answer."
2. If the report shows only one total, ask: "Which of these three amounts was in euros? What did we do about it?"
3. If the learner is unsure whether to use net or gross, point at the Norden invoice: reverse charge means no VAT, so net equals gross. For the two Polish invoices the report uses net so the three suppliers are comparable; show gross in a second column if they want.

## What you just learned

You fetched a real number from outside your files, made the method reusable as a skill, and wrote down where the number came from. You also met the three ways an agent can reach outside data and learned that the simplest one often wins for a single public number.

**Bring it to your job:** pick one number you copy by hand from a website every week or month, and ask your mentor which of the three ways fits it best.

## Mentor reference

**NBP check (done 2026-11-08):** `https://api.nbp.pl/api/exchangerates/rates/a/eur/2026-10-09/?format=json` returns HTTP 200: table no. `197/A/NBP/2026`, effectiveDate `2026-10-09`, mid `4.3775`. For comparison, 2026-10-02 returns table `192/A/NBP/2026`, mid `4.3745`. For 2026-10-10 (a Saturday), and for a public holiday such as 2025-11-11, the API returns HTTP 404 with the text "404 NotFound - Not Found - Brak danych". The correct fallback is to step back one calendar day at a time until a 200 comes back (so 2026-10-10 gives the rate of 2026-10-09, 4.3775), and to print the date the rate is really from. The invoice date 2026-10-09 is a Friday, so no fallback is needed for the actual task. Confirm it live if the learner's run is later: the numbers for past days do not change. If the network is blocked, use the numbers above as the fallback and say so in the source line.

**Skill expectations:** takes currency and date; calls the NBP address; on 404 steps back, up to about 10 days; prints rate, effective date, table number; stops with a clear message on any other error (no invented rate).

**Expected numbers:**

| Supplier | Currency | Net | PLN net |
|---|---|---|---|
| Vistula Paper (VP-2026-1187) | PLN | 6,098.00 | 6,098.00 |
| Baltic Pack (BP-44120) | PLN | 6,226.00 | 6,226.00 |
| Norden Clean (NC-2026-0912) | EUR | 3,179.50 | 13,918.26 |

Norden conversion: 3,179.50 x 4.3775 = 13,918.26125, rounded to **13,918.26 PLN**. Total net spend: **26,242.26 PLN**. If the learner used gross for the Polish invoices: 7,500.54 and 7,657.98 (total 29,076.78 with Norden). Either is fine if labeled.

**Source line must contain:** EUR/PLN 4.3775, NBP table A no. 197/A/NBP/2026, rate date 2026-10-09, applied to invoice NC-2026-0912.

**Common misses:** rate recalled from memory instead of fetched; Norden left in EUR in the chart; two decimals missing; source line without table number or date; the 404 case described as "the site is down".
