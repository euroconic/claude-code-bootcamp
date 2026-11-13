# Mission 3C - Safe Access: Permissions, Keys, and What Never Goes to an Agent

> Mentor: stretch mission of session 3, and the answer to the open-group question "is it safe to connect my tools?". Corvane IT wants a one-page safe-use note before the AI working group connects the tracker and the ERP. The learner writes it. Keep it practical: four decisions (what data, what access, where keys live, what is wrong in a draft). Do not lecture on security theory. If the learner brings real company data or a real key, stop and remind them of the "Never paste real secrets" rule in `START-HERE.md`: describe the file instead.

## Goal

Write a one-page safe-use note, `workspace/work/safe-use-note.md`, with four parts: a green/amber/red sorting of data, the access level each connection needs, a rule for where keys live, and the problems you found in a draft connection file.

## Why it matters

Connecting an agent to real tools is where most of the risk sits. A connection is a door: the agent can do whatever that door allows, as fast as it can type. Three habits cover most of it: give the agent only the data it needs, give each door the lowest access that gets the job done, and keep passwords out of every file and every chat. IT will approve a connection much faster when the people asking already know these three rules.

Plain words for four terms:

- **Read-only access:** the agent can look but not change anything. **Write access** lets it add, edit, or delete.
- **Key or token:** a long code that works like a password for programs. Whoever holds it can act as you.
- **Environment variable:** a named setting kept by your computer, outside your project files. A program reads it when needed. The key never appears in a file you share.
- **Commit:** a saved snapshot of your project (you met it in Mission 09). Once a key is in a snapshot that gets shared, it should be treated as public.

## What to do

1. Open `data/corvane/s3/data-items-to-classify.md`. Read the twelve items and the three colors. Before asking the agent, put your own color next to each item on paper or in your head.
2. Compare notes:
   > "Read data/corvane/s3/data-items-to-classify.md. For each of the twelve items, suggest green, amber or red and give the reason in one line. Where you are unsure, say so instead of guessing."
   Disagree where you think the agent is wrong, and decide the final color yourself. For every amber item, write what exactly must be removed or trimmed first.
3. Decide the access level. Open `data/corvane/s3/connector-config-draft.md` but look only at the `purpose` line of each of the four connections (tracker, shared drive, ERP export, exchange-rate site). For each one write: read-only or write, how much (everything or one project, folder, or file), and a reason in one sentence. Rule of thumb: start with read-only and the smallest slice. Ask IT for more later, when you can name a real task that needs it.
4. Learn where keys live:
   > "Explain in plain words, for a non-coder, where a token for a tool like our tracker should be kept, and where it must never be. Cover: pasted into this chat, written into a file in the project, a note on my desktop, an environment variable, and the tool's own connection settings. Then tell me what to do if a token has already been shown in a chat or saved in a shared file."
   Write the rule in two or three lines for the note.
5. Find the planted problems. Now read the whole of `connector-config-draft.md`:
   > "Review data/corvane/s3/connector-config-draft.md as an IT security reviewer. List every problem, most serious first. For each one, say what could go wrong and how to fix it. Do not change the file yet."
   Compare with your own findings from step 3. Did you spot anything the agent missed?
6. Fix it safely:
   > "Write a corrected copy to workspace/work/connector-config-fixed.md. Replace the token with a reference to an environment variable called CORVANE_TRACKER_TOKEN (no real value). Set access to the lowest level that fits each purpose. Narrow every scope. Do not invent any key."
7. Write the note:
   > "Create workspace/work/safe-use-note.md, one page, for Corvane IT. Four sections: 1) Data: the green, amber and red lists, and for each amber item what is removed first; 2) Access: a table of the four connections with read-only or write, scope, and reason; 3) Keys: where they live and where they never go, and what to do if one leaks; 4) Problems found in the draft config and how they were fixed. Plain words. No real keys."
8. Check it as the reader. Ask: "If I were the IT person with five minutes, could I approve or reject a connection from this page alone? What is missing?" Fix the gaps.

## Definition of Done

`workspace/work/safe-use-note.md` exists and:

- Classifies all twelve data items as green, amber or red, with a reason each, and says what is removed for every amber item.
- Gives an access level (read-only or write), a scope and a reason for each of the four connections.
- States that keys are never pasted into chat or saved in a file that gets committed or shared, names at least one safe place (an environment variable or the tool's own connection settings), and says what to do if a key leaks (treat it as public, have it replaced, tell IT).
- Names the planted problems in the draft file (see Mentor reference), at least the key written into the file.
- Contains no real key or real company data. The fake token may be mentioned only by its placeholder name.

`workspace/work/connector-config-fixed.md` exists and contains no token value.

## Hints (mentor: one at a time)

1. Stuck on a color? Ask: if this file were printed and left on a train, who would be upset?
2. Learner wants write access "just in case"? Ask: what is the first task that needs to write? Can a person do that one step instead?
3. Learner says the draft key is fake so it does not matter? Say: right, it is fake here, but the habit is what counts. Ask: if it were real and this file went to the team's online storage tonight, who could read it?

## What you just learned

Safe use comes down to four small decisions: what data goes in, what each connection may do, where keys live, and who reviews the setup. None of them needs technical skill. Bring a page like this to IT and the conversation about connecting your tools gets short.

**Bring it to your job:** list the three tools you would most like an agent to reach. For each, write read-only or write, and what exact slice of data it needs.

## Mentor reference

Expected classification of the twelve items (accept a defensible alternative if the learner gives a reason, but red items must not move):

- Green: 1 exchange-rate table, 2 public product catalogue, 3 policies folder, 4 draft requirements document.
- Amber: 5 tracker export (remove or replace owner names), 6 purchase-order export (supplier names and negotiated prices only if IT has approved the tool for company data; otherwise round or mask), 7 supplier invoices (remove the bank account number), 8 call transcript (remove names and the remarks about colleagues).
- Red: 9 customer file with phone numbers and home addresses of private persons, 10 salary and bonus table, 11 the note with the token, 12 contract in a legal dispute.

Expected access levels:

- Tracker: read-only, only the project needed (the change-request project). Writing comments or moving tickets is a later step, with a person approving.
- Shared drive: read-only, only the "Policies" folder, not the top of the drive.
- ERP export: read-only, the one nightly export file. Never direct write access to the ERP.
- Exchange-rate site: read-only, public, no key needed.

Planted problems in `connector-config-draft.md` (the first one is the main one):

1. The tracker token is written into the file as plain text (`CORVANE-TRACKER-TOKEN-EXAMPLE-NOT-REAL-0000`, fictional), and the file is copied every night to the team's online storage. If it were real it would have to be treated as leaked: replaced and reported to IT. Fix: environment variable or the tool's connection settings.
2. Tracker access is read-write while the purpose is only reading.
3. Tracker scope is "all projects" while the report needs one.
4. Shared drive access is read-write.
5. Shared drive folder is "/" (the whole drive, including HR and legal folders) while the purpose is policies only.
6. The colleague's note "so we never have to ask IT again" is the wrong reasoning: it removes IT's review.

The ERP export and the exchange-rate connections are fine as drafted. A learner who flags them as problems should explain why, or drop it.

The fixed copy must use an environment variable name only (for example `CORVANE_TRACKER_TOKEN`), no token value. If the learner pastes a string that looks like a real key anywhere, stop and have them remove it.
