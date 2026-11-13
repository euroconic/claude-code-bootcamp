# Session 3 - Outside Data: MCP, API, or a Script

## Theme of the live session

So far your agent worked with files you handed it. Real work also needs data that lives somewhere else: an exchange rate on a public website, tickets in a tracker, numbers in a company system. This session shows the three ways an agent can reach that data, and how to pick the right one.

Plain-words version (think of a shop):

- **MCP connection** is a **service counter**. The tool (Jira, Slack, a database) has a counter built for agents. You connect once, and the agent can ask for things in a standard way. Setup usually needs an account and a token (a secret password for programs).
- **API** is a **delivery door**. A website lets programs knock and ask for specific data in a fixed format. Anyone can build something that knocks. Public ones need no password; private ones need a key.
- **A skill with a small script** is **your own errand runner**. You write down (with the agent's help) exactly how to go and fetch the data, save it as a skill, and call it by name from then on. The runner can use an API or read a file, whatever works.

When to use which:

| Situation | Best fit |
|---|---|
| One public number, same lookup again and again (an exchange rate) | Skill with a small script calling the public API |
| A tool your company already uses, with many kinds of questions (tickets, chats) | MCP connection, if IT allows it |
| You only have a file someone exported | Just read the file. Wrap it in a skill if you repeat it |
| Data you are not allowed to send outside | None of these. Ask your security contact first |

MCP setup with tokens is **optional** in this session. You never need it to pass. Every mission here works with a public API or a file.

## Missions

| Mission | Time | Core? | What you do |
|---|---|---|---|
| [3A](MISSION-3A.md) Exchange-rate skill and spend report | 30-40 min | Core | Build the `fx-rate` skill, convert the Norden invoice to PLN, produce a spend report |
| [3B](MISSION-3B.md) Weekly change-request report | 30-45 min | Stretch | Turn a tracker export into the Friday status report |

Finished work goes into `workspace/work/`. Data is in `data/corvane/s1/` (3A) and `data/corvane/s3/` (3B).
