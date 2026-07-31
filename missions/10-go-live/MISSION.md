# Mission 10 — Go Live (Bonus)

> Mentor: this mission is OPTIONAL and the learner knows it. Do a prerequisite check FIRST and be honest: if they do not want to install anything or make an account, congratulate them on finishing the core course and point them to the Capstone. If they do want to ship it live, walk them through the simplest path. Never make them feel they failed by skipping this.

## Goal
Put your landing page on the public internet with a real URL you can send to anyone, using Vercel or GitHub Pages (both free hosting options).

## Why it matters
A landing page on your laptop tests nothing. A landing page with a public link can be shared, posted, and measured, which is how you actually validate demand. Getting from "it works on my machine" to "here is the link" is the last mile that most people never cross. You are about to cross it.

## Before you start (prerequisite check)
This is the one mission that needs a couple of real-world things. Your mentor will check with you:
- **Node.js installed?** (a free tool the Vercel command line needs). If not, your mentor can point you to https://nodejs.org or you can use the drag-and-drop option below.
- **A free Vercel account?** Sign up at https://vercel.com (free for personal projects).

If you would rather not install or sign up for anything, that is completely fine. You have finished the real course. Type `next` to go to the Capstone.

## What to do (pick the easier path for you)

### Path A — Drag and drop (no command line, easiest)
1. Go to **https://vercel.com/drop** (this is Vercel's dedicated drag-and-drop page, no GitHub repo needed). Log in if asked.
2. Your landing page is the folder `workspace/mvp/`. Ask your mentor: "which folder do I drag to vercel.com/drop?" (answer: the `workspace/mvp` folder).
3. Drag that folder onto the page. You get a live URL in under a minute.

> Note: do NOT use the generic dashboard "Add New Project" flow for this. That one expects your code to be in a GitHub repository, and your MVP is just a local folder. Vercel Drop is the route that works for a plain folder.

### Path B — Command line (with Node installed)
1. Ask your mentor: "walk me through deploying workspace/mvp to Vercel using the Vercel CLI, step by step, and explain each command." It will typically be:
   - `npm install -g vercel` — installs the Vercel command-line tool, once, globally on your computer.
   - `vercel login` — signs the CLI into your Vercel account (opens your browser to confirm).
   - `cd workspace/mvp && vercel --prod` — deploys the folder straight to a live, public URL.
2. Your mentor will run these for you and explain each one as it goes, and decode any prompts.
3. Do not panic at red text, it is usually normal. The usual culprits if something fails are: wrong folder, or not logged in yet.

### Path C — GitHub Pages (if you already pushed to GitHub in Mission 09)
If you completed the optional GitHub step in Mission 09, GitHub itself can host your page for free, no separate account needed:
1. Ask your mentor: "walk me through turning on GitHub Pages for my repo so workspace/mvp/index.html is live."
2. Typically: in your repo on GitHub, go to Settings > Pages, set the source to your branch, and (since the page lives in `workspace/mvp/`) point the folder there or move/copy `index.html` to where Pages expects it. Your mentor will tell you exactly which, based on how your repo is laid out.
3. GitHub gives you a `github.io` URL a minute or two after you save the setting.

## Definition of Done
- A live, public URL exists that shows your Signal landing page, OR
- The learner consciously chose to skip the bonus (also a pass).

## Hints (mentor: one at a time)
1. Path A (drag and drop) is the lowest-friction route for non-technical learners. Suggest it first, unless they already have a GitHub repo from Mission 09, in which case Path C is a nice one-click-setting option.
2. Because the MVP is a single static `index.html`, no special config is needed. Vercel and GitHub Pages will both serve it as-is.
3. If a deploy fails, the usual culprits are: wrong folder selected, or not logged in. Check those first.
4. Celebrate the live URL hard. Sending a real link to a real product is a genuine "I made this" moment.

## What you just learned
You can take something from your laptop to a public URL anyone can open. Shipping is a skill, and you just did it.
