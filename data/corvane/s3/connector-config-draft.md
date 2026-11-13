# Connector Config Draft (Corvane, session 3)

Fictional. A colleague on the AI working group wrote this draft before IT's safe-use note existed. It describes the four connections the group wants to set up. The draft is saved in the working group's shared project folder, which is copied to the team's online code storage every night (so everyone on the team can read it).

Nobody has used it yet. One more person will look at it before it goes live: you.

```yaml
# corvane-agent-connections.yaml
# Draft by the AI working group. Fill in, then send to IT for approval.

connections:

  tracker:
    purpose: "Read change requests to build the Friday status report"
    address: "https://tracker.corvane.example"
    token: "CORVANE-TRACKER-TOKEN-EXAMPLE-NOT-REAL-0000"
    access: "read-write"
    scope: "all projects"

  shared_drive:
    purpose: "Read policy documents to answer staff questions"
    address: "https://files.corvane.example"
    folder: "/"
    access: "read-write"

  erp_export:
    purpose: "Read the nightly purchase-order export to check invoices"
    address: "file share: \\\\corvane-erp\\exports\\purchase-orders-nightly.csv"
    access: "read-only"
    scope: "the one export file"

  exchange_rates:
    purpose: "Look up official EUR/PLN rates"
    address: "https://api.nbp.pl"
    access: "read-only"
    key: "none needed, public service"
```

Notes from the colleague:

- "The token is pasted in so nobody has to hunt for it later."
- "Read-write everywhere, so we never have to ask IT again when we want the agent to add a comment or move a file."
- "Folder is the top of the drive so it can find any policy."
