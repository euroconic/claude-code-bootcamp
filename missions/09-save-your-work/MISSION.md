# Mission 09 — Save Your Work

> Mentor: introduce git gently as "save points for your whole project", not version control theory. The learner has likely never used git. Walk them through init, add, commit with the assistant running the commands. Decode any scary output. This also sets them up for Mission 10 (deploy).

## Goal
Save your whole project properly using git, so your work is captured in a clean snapshot you could share, restore, or publish.

## Why it matters
Up to now your files just sit in a folder. **Git** is a tool that takes labeled snapshots of your whole project, so you can always go back, see what changed, and share it. Every software team on earth uses it, and it is the on-ramp to publishing your MVP online (Mission 10). Learning the three basic moves demystifies a thing that intimidates a lot of non-engineers.

## What an analogy helps here
Think of git like "save game" checkpoints for a project. A **commit** is one save point, with a note about what you did. A **repository** (repo) is just your project once it is under git's care.

## What to do
1. Ask your mentor: "is this project using git yet?" If not: "set up git for this project."
2. Set your identity (one-time, required before your first ever commit, or git will stop with an "unknown author" error). Ask your mentor: "set my git name and email." The commands it runs are:
   > `git config --global user.name "Your Name"` and `git config --global user.email "you@example.com"`
   If you have committed on this computer before, this is already done and you can skip it.
3. Take your first snapshot. A strong prompt:
   > "Initialize git here if needed, then stage everything and make a first commit with the message 'Signal bootcamp: research, decision, PRD, and MVP'. Then show me the log so I can see my save point."
4. Make a tiny change (edit a line in your PRD), then ask: "show me what changed since my last commit, then commit it with a clear message." This is the loop: change, review, commit.
5. Ask your mentor to explain the three core moves in one line each: `add` (choose what to save), `commit` (save with a note), `log` (see your history).
6. **(Optional) Publish your version to your own GitHub.** This turns your work into a public portfolio piece and sets up the graduation step in the capstone. A repository on GitHub is just your project, stored online so you can share it with a link. If you do not have a GitHub account yet, your mentor will walk you through it. Then:
   > "Create a new public GitHub repo called signal-bootcamp under my account and push this project to it. Show me the link when it is live."
   Your mentor can do this for you with the `gh` command-line tool (it will install or sign you in if needed). Keep the repo public so you can share it and add it to the showcase later.

## Definition of Done
- The project is a git repository with at least one commit (`git log` shows it).
- The learner can explain, in their own words, what a commit is.
- (Optional) The project is pushed to a public GitHub repo and the learner has the link.

## Hints (mentor: one at a time)
1. There is already a `.gitignore` in this project so junk files stay out of the snapshot. Mention what it does in one sentence.
2. If git asks for a name/email on first commit, walk them through setting it, it is a one-time thing and not scary.
3. Keep commit messages plain and descriptive. "stuff" is a bad message; "add data-insights and decision memo" is a good one.

## What you just learned
Git gives your project labeled save points you can return to and share. Three moves cover most of real life: add, commit, log. You are no longer afraid of the word "repository."
