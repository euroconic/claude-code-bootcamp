# Mission 08 — Build the MVP

> Mentor: this is where a non-technical person builds a real, working web page and sees it in their browser. Keep it to a single self-contained index.html (plain HTML + Tailwind via CDN), no build tools, no npm, no framework. The page should reflect THEIR PRD (their positioning, their wedge, their target user). After building, tell them exactly how to open it (double-click the file, or "open it for me").

## Goal
Build a working landing page MVP for Signal: a single web page that pitches the product and captures interest (a waitlist email field). It should open in a browser with a double-click.

## Why it matters
The fastest way to test demand is not to build the product, it is to build the promise: a landing page that says what the product does and asks "want in?" Real founders validate ideas this way before writing a line of real code. You are about to ship a tangible thing built from your own research and PRD.

## What to do
1. Tell your mentor to base the page on your `PRD.md` (headline, the wedge, the target user, the top features).
2. Ask for the build. A strong prompt:
   > "Build a single-file landing page at workspace/mvp/index.html for Signal, based on my PRD.md. Use plain HTML and Tailwind via CDN so it opens with a double-click, no build step. Include: a clear headline and subhead from our positioning, 3 feature highlights from the PRD, a short 'how it works' section, and a waitlist email signup form. Make it look clean and modern."
3. Open it: ask "open workspace/mvp/index.html in my browser" (or double-click the file yourself).
4. Iterate like a designer: "make the headline punchier", "change the accent color to teal", "add a one-line social proof quote from our interview." Watch it update.

## Definition of Done
- `workspace/mvp/index.html` exists and opens in a browser as a coherent landing page.
- The content reflects the learner's own positioning/PRD (headline, features, target user), not generic filler.
- It has a waitlist/email capture element.

## Hints (mentor: one at a time)
1. One file, no tooling. Tailwind via the CDN script tag keeps it double-clickable. Avoid anything that needs `npm install`.
2. The page should echo their PRD. If the headline is generic, point them back to their positioning sentence from Mission 03.
3. Encourage at least two visual iterations so they feel the "design by conversation" loop.
4. The waitlist form does not need a real backend for the MVP. A simple form that shows a "thanks, you're on the list" message on submit is enough.

## What you just learned
You can build and restyle a real, working web page by describing it, then refine it like talking to a designer. Validating demand no longer requires an engineer.
