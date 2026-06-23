# Mission 01 — Create an Agent

> Mentor: this is a **"watch me, then you try"** mission. First show the learner the example agent, explain it in plain language, then have them build (or customize) their own and run it once. This is the highest take-home-value mission in the course, make it land.

## Goal
Build your own reusable AI agent: a saved teammate with a fixed job, that you can call on any time. You will pick one of three practical agents and create it for real.

## Why it matters
So far you have been giving the assistant one-off instructions. An **agent** is different: it is a job description you save once, so you never have to re-explain it. Real example: instead of writing "turn these notes into a status update, keep it short, group by project, flag risks" every Friday, you build a "Status Writer" agent once and just say "use my status writer on these notes." This is how people quietly save themselves hours a week.

## What an agent actually is (plain version)
An agent is just a small text file with two parts:
- **A name and a description** (so the assistant knows when to use it).
- **Instructions** (the job: what it does, the tone, the format).

In Claude Code these files live in a folder called `.claude/agents/`. The dot at the front just means "config" (it is a hidden folder, so do not worry if you cannot see it in Finder). If that folder does not exist yet, your mentor will create it for you. That is normal. You do not need to understand more than that.

There is a ready-made example for you in this mission's `templates/status-writer.md`. Look at it, it is short and readable.

## What to do

### Step 1 — Watch (mentor demonstrates)
Ask your mentor: "show me the example status-writer agent and explain each part." Your mentor will walk you through the template line by line.

### Step 2 — Choose your agent
Pick the one most useful to your real job (or invent your own):
1. **Status Writer** — turns rough bullet notes into a crisp weekly team status update.
2. **Management Reporter** — turns project notes into a short, calm exec/management report (decision-focused, no fluff).
3. **Jira Story Writer** — turns a feature idea into well-formed user stories (As a [user], I want [x], so that [y]) with acceptance criteria.

### Step 3 — Build it
Tell your mentor which one you chose and say: "help me create this as an agent in `.claude/agents/`." Together you will write the name, description, and instructions. Make the tone and format match how YOU actually work.

### Step 4 — Run it once
Test it on real-ish input. For example, paste 4-5 messy bullets about your week and say "use my status writer agent on these." See it work. Save the output to `workspace/agent-sample-run.md`.

## Definition of Done
- A new agent file exists in `.claude/agents/` (any sensible name, e.g. `status-writer.md`) with a name, a description, and real instructions.
- A sample output from running it is saved at `workspace/agent-sample-run.md`.

## Hints (mentor: one at a time)
1. Start from the template, do not write from a blank page. Copy `templates/status-writer.md` and adapt it.
2. The description should say WHEN to use the agent ("Use when turning weekly notes into a team status update"). That is what makes it trigger reliably.
3. Good instructions are specific about format: how long, what sections, what tone, what to leave out.
4. If they are stuck on input to test with, offer to invent 5 realistic bullets for their role.

## What you just learned
You can package any repeatable task into a reusable agent: write the job description once, run it forever. This alone is worth the price of admission, and it works on your real job tomorrow.
