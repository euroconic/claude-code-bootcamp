# Mission 3B - Weekly Change-Request Report

> Mentor: stretch mission. The learner turns a tracker export into the report Tomasz builds by hand every Friday. The skill being practiced is giving the agent exact rules ("overdue" means this, "stale" means that), then checking the lists against the data. Watch for the traps in the Mentor reference: non-CR rows, finished items, and a boundary case.

## Goal

Read `data/corvane/s3/tracker-export.csv` (an export from Corvane's task tracker, 30 rows) and write `workspace/work/cr-weekly-2026-10-24.md`: a weekly report on change requests only, for the report date **2026-10-24**.

## Why it matters

Every Friday Tomasz Wren, who runs the change-request process, copies a tracker export into a document and counts by eye. It takes an hour, and the lists differ from week to week because the rules live in his head. When the rules are written down and the agent applies them, the report takes a minute and anyone can check it.

## What to do

1. Open the CSV and skim it. A **CR** is a change request: a formal ask to change a system or process. Rows of type Bug and Task are also in the file, but this report is about CRs only.
2. Give the agent the rules in plain words. Do not let it invent them:
   > "Read data/corvane/s3/tracker-export.csv. The report date is fixed: 2026-10-24. Look at change requests only (type CR). Before you build anything, tell me in your own words how you would decide: (a) overdue, (b) over budget, (c) stale, (d) no owner. Ask me if a rule is unclear."
3. Give your definitions and ask for a plan:
   > "Use these rules, for CRs that are not Done. Overdue: due date before 2026-10-24. Over budget: spent_days greater than estimate_days. Stale: last updated more than 14 days before 2026-10-24. Needs an owner: owner is empty. Show me the plan first, do not write the report yet."
4. Build the report:
   > "Create workspace/work/cr-weekly-2026-10-24.md with: (1) count of CRs by status, (2) overdue list, (3) over-budget list, (4) stale list, (5) items needing an owner, (6) a 3-line summary for the COO. In every list give key, summary, owner, and the reason (for example 'due 2026-10-20, 4 days late'). Say clearly if a CR is on more than one list."
5. Check it. Pick two CRs from the CSV and verify them by hand. Then ask:
   > "Re-read the CSV. Did you include any Bug or Task by mistake? Did you include any Done item in the lists? Count each list again and show the keys."
6. Ask for the box at the end of the report. Say:
   > "Add a short box titled 'With a real tracker': explain in plain words how the same report would work through an MCP connection to a tracker like Jira, what it would need (an account and a token, plus IT approval), and why starting from a CSV export is a safe first step."
7. Optional: save the rules as a skill called `cr-weekly` so next Friday you only say "run cr-weekly on this export".

## Definition of Done

- `workspace/work/cr-weekly-2026-10-24.md` exists with the six parts above and the "With a real tracker" box.
- Only CR rows are used, and no Done item is in a problem list.
- The counts and keys match the Mentor reference.
- The 3-line summary is readable by a COO: numbers, not a list of keys.

## Hints (mentor: one at a time)

1. If the lists look too long, ask: "Did you include Bugs and Tasks? The report is for change requests."
2. If a CR on the wrong list is Done, ask: "Is a finished item overdue?"
3. For the stale rule, ask the learner to count days for one item. Exactly 14 days is not stale; 15 is.

## What you just learned

An agent applies rules well when you state them exactly and let it show its plan first. You also learned that a CSV export is a fine, safe way to start: it needs no account and no token. A connection to the live tracker (MCP) comes later, when the report works and the team wants it fresh without the export step.

**Bring it to your job:** write down your own weekly report's rules (what counts as late, what counts as stale), and let the agent apply them to your next export.

## Mentor reference

Counts for report date 2026-10-24 (the generator in `tools/work_track_data/s3/` prints the same numbers). The file has 30 rows: 16 CR, 6 Bug, 8 Task. Lists use CRs that are **not Done**.

**CRs by status (16):** Backlog 4, In progress 6, In review 2, Blocked 2, Done 2.

| List | Count | Keys (summary) |
|---|---|---|
| Overdue | 4 | COR-102 (Daily ERP export of purchase-order lines, due 2026-10-20), COR-104 (Payment hold flag in ERP, due 2026-10-18), COR-114 (EUR conversion at invoice-date rate, due 2026-10-22), COR-125 (Purchase order change log, due 2026-10-23) |
| Over budget | 3 | COR-102 (9.5 of 8 days), COR-106 (Credit note approval workflow, 11 of 10), COR-125 (10.5 of 10) |
| Stale | 3 | COR-107 (Supplier onboarding form update, updated 2026-10-01), COR-115 (Delivery note matching, 2026-10-03), COR-117 (Return reason codes, 2026-10-09, 15 days) |
| Needs an owner | 2 | COR-112 (Archive rules for old invoices), COR-120 (Buyer notification for disputed lines) |

**On two lists:** COR-102 and COR-125 are both overdue and over budget. They are the headline for the COO.

**Traps the learner should not fall into:**
- COR-109 (Done) is over budget, 9 of 7 days. It is finished, so it is not listed.
- COR-124 (Supplier scorecard) was updated 2026-10-10, exactly 14 days ago. Not stale.
- Eight Bug or Task rows would match a rule if type were ignored: COR-103, 108, 110, 113, 118, 121, 128, 130. None belongs in the report.
- COR-114 (due 2026-10-22, In review) is overdue by 2 days even though it was updated yesterday.

**Summary for the COO should say roughly:** 14 open CRs, 4 overdue (2 of them also over budget), 3 stale, 2 without an owner; the main risks are the ERP export (COR-102) and the purchase order change log (COR-125); action needed: assign owners to COR-112 and COR-120.

**"With a real tracker" box:** should mention an MCP connection to the tracker, a token and IT approval, the agent asking the tracker directly for the same fields, and that the CSV path keeps working as a fallback and a way to test the rules.
