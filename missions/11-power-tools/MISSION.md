# Mission 11 — Power Tools (Bonus)

> Mentor: this mission is OPTIONAL, like Mission 10, and the learner knows it. It is the one mission that is not about the Signal case, it is about Claude Code itself: two features (Skills, Subagents) that make you meaningfully faster on real work once you know they exist. Go one concept at a time, do not dump both definitions in the same message. This is a good moment to be genuinely enthusiastic, these are the "insider" tricks.

## Goal
Get hands-on with two Claude Code features you have been using indirectly this whole course without naming them: **Skills** and **subagents**. Run a real skill on your own work, and understand what a subagent is.

## Why it matters
So far you have typed things in plain English and Claude has figured out how. Skills and subagents are how Claude Code stays fast and reliable as tasks get bigger: a Skill is a packaged, tested way of doing a specific job well; a subagent is a helper Claude spins up to go do a chunk of work on its own and report back. Knowing these exist means you can reach for them on your real job instead of re-explaining a task from scratch every time, or wondering why a big request took a while.

## What to do

### Step 1 — Skills
A **Skill** is a pre-built playbook for a specific job, like a recipe Claude can follow instead of improvising every time. You trigger one by typing `/` followed by its name, or sometimes Claude reaches for one on its own when it recognizes the job. You have benefited from skills already without seeing them named.

Ask your mentor: "what skills are available in this environment, and what do they do?" Skim the list, most will not mean anything to you yet, and that is fine.

### Step 2 — Run a security skill for real
One especially useful one is a **security review** skill: it reads code or configuration and flags real risks (like a page that would leak data, or a form that is unsafe). Ask your mentor:
> "Run a security review on my workspace/mvp/index.html and summarize what it finds in plain English."

Even a simple static landing page can turn up a note or two (or a clean bill of health). Either result is useful: this is the same kind of check a company would run before anything real goes live, and now you have seen it happen on something you built.

### Step 3 — Subagents
While you have been working through this course, on a few research-heavy asks (market research, data analysis) Claude Code may have quietly used a **subagent**: a separate helper instance of Claude, given a narrow job and a deadline, that goes off, does that one piece of work, and comes back with a result. It exists so the main conversation with you does not get cluttered with someone else's homework, only the answer.

Ask your mentor: "did you use any subagents during this course, and what is the difference between a subagent and the custom agent I built in Mission 01?" (Short answer to expect: your Mission 01 agent is a saved job description that Claude reads when you call on it by name. A subagent is a temporary helper Claude itself decides to spin up mid-task to go research or execute something in parallel, then it reports back and disappears.)

### Step 4 — Build your own skill (pointer, not required)
If this clicked for you, there is a skill called **skill-creator** that walks you through building your own custom skill, the same way Mission 01 walked you through building your own agent. You do not need to do this now, just know it exists: "there's a skill-creator skill whenever I want to package one of my own recurring tasks."

### Step 5 — Write it down
Ask your mentor to save a short summary to `workspace/power-tools-notes.md`: the security review findings from Step 2, and, in your own words, one or two sentences on what a subagent is and how it differs from a Mission-01-style agent.

## Definition of Done
- `workspace/power-tools-notes.md` exists.
- It contains the security review output/summary from Step 2.
- It contains a short explanation, in the learner's own words, of what a subagent is.

## Hints (mentor: one at a time)
1. If the learner is not sure what to ask for the security review, offer to run it on their MVP first since it is small and already built.
2. On subagents, keep the distinction concrete: "the agent you built is a job description you call by name; a subagent is Claude delegating to itself mid-task." Do not over-explain the mechanics underneath.
3. If they want to try skill-creator for real, let them, but do not let it block finishing this mission's Definition of Done.

## What you just learned
Skills package up expert-level playbooks you can call on by name, including things like automated security checks. Subagents are how Claude quietly handles bigger jobs without cluttering your conversation. You now know both exist, which means you will recognize when to reach for them on your real work.
