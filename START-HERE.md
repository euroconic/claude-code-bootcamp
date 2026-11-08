# Start Here - AISandboxLab.com Claude Code Bootcamp

A Claude Code Bootcamp by [AISandboxLab.com](https://AISandboxLab.com).

Welcome. By the end of this you will have run real market research, analyzed real data, written a PRD, built a working web page, and (optionally) published it live on the internet. All by talking to an AI assistant in plain English. No coding background needed.

You will be playing a role: **founding Product Manager at a startup called "Signal."** Every task moves your product forward. It feels like a real project because it is built like one.

---

## What you need (5 minutes of setup)

1. **Claude Code installed.** Not installed yet? Follow the [Quick Guide: INSTALL.md](INSTALL.md) - it takes 5-10 minutes from zero. (Or see https://docs.claude.com/claude-code.)
2. **This folder, unzipped**, somewhere you can find it (Desktop is fine). Do not have it yet, and never used GitHub? Follow the [Quick Guide: GET-THIS-PROJECT.md](GET-THIS-PROJECT.md) - no account needed, 2 minutes.
3. **15-20 minutes per mission.** There are 11 core missions, two optional bonus stops (Go Live and Power Tools), and a capstone wrap-up. Do one a day or binge them. Your progress is saved.

---

## How to start (do this exactly once)

1. Open your terminal.
2. Go into this folder. The easiest way: type `cd ` (with a space), then drag this folder onto the terminal window, then press Enter.
3. Type `claude` and press Enter.
4. When Claude is ready, type this and press Enter:

   ```
   begin
   ```

That is it. Your AI mentor will greet you, figure out where you are, and hand you your first mission.

---

## Three ways to run Claude Code (pick whatever feels comfy)

Claude Code is the same tool no matter where you open it. The steps above use the terminal because it always works, but you have options. Use the one that feels least scary.

| Where | How to open this folder | Best for |
|-------|-------------------------|----------|
| **Terminal** | `cd` into this folder, type `claude`, press Enter (the steps above) | Everyone. Always works, nothing extra to install |
| **VS Code** | Install the Claude Code extension from the Extensions panel, open this folder (File > Open Folder), then start Claude from the side panel or the command palette | People who like seeing their files in a sidebar while they work |
| **Claude Desktop app** | Open the Claude desktop app, point it at this folder, and start a Claude Code session there | People who prefer an app window over a terminal |

Whichever you choose, the rule is the same: **Claude Code must be opened inside this course folder.** That is how your mentor "wakes up" and knows it is the mentor. If you ever feel lost, the terminal steps above are the safe default.

**Why bother with VS Code?** The terminal only shows text. VS Code adds a sidebar with every file and folder in the project, so you can see the shape of what you're building, and it can show a markdown file (like this one) formatted nicely instead of raw text with `#` symbols everywhere. Click the little preview icon in the top-right of an open markdown file to see it rendered; click back on the file's tab to get back to plain-text edit mode. Neither view changes the file, it is just how you are looking at it.

---

## A few Claude Code basics worth knowing

You drive Claude Code mostly by talking in plain English. A handful of small tricks make life much easier, and you will use them in the missions.

**1. Slash commands.** Type a `/` (forward slash) and a little menu of built-in commands pops up. You do not need to memorize them. A few handy ones:

- `/help` - shows what you can do
- `/clear` - wipes the conversation and starts fresh (useful if things get messy)
- `/compact` - shrinks a long conversation down to a summary instead of a full wipe, handy if things are getting slow but you are not ready for `/clear`

You will see other slash commands appear. Ignore the ones that look technical or unrelated to the course; your mentor will tell you if a mission ever needs one.

**2. Pointing at files.** Often you will want Claude to look at a specific file (a transcript, a spreadsheet, a page you made). Two easy ways to do that:

- **Type `@`** and start typing the file name. Claude shows a list, you pick the file. This "mentions" the file so Claude reads it.
- **Copy or drag the file's path.** Drag a file onto the terminal window and its full path appears, or right-click a file and copy its path, then paste it into your message. Saying "look at this file: <pasted path>" works perfectly.

**3. The Esc key.** If Claude is mid-response or mid-action and heading somewhere you did not want, press `Esc`. It stops what it is doing right there. Nothing is lost, you just get control back to redirect it.

**4. Where does Claude live right now?** This Claude Code session runs locally, right here in this folder, reading and writing your actual files. That is different from chatting with Claude on claude.ai in a browser, which never touches your computer. Both are "Claude," just set up for different jobs, this one is set up to work directly in your project.

**5. Getting better answers.** The single biggest lever is being specific: name the exact sections or format you want, and if the first answer is close but not quite right, say so and ask for the change rather than starting over. Every mission gives you a "strong prompt" example, notice how specific they are, that is the pattern.

**6. Planning before building.** On anything bigger than a one-line edit, you can ask Claude to lay out its plan or its options before it touches a single file, so you are steering instead of reacting after the fact. Just say something like "make a plan first" or "give me a few options before you build anything." There is also a dedicated **Plan Mode** built into Claude Code for this, your mentor can show you how to turn it on when a mission calls for it (Mission 08 is a good place to try it).

**7. Choosing a model.** Claude Code can run on different underlying Claude models, some faster, some more powerful for gnarly reasoning-heavy work. Type `/model` any time to see and switch which one you are talking to. You do not need to touch this for this course, the default is a good fit for everything here, just know the option exists for your real job later.

**8. Choosing a mode.** Beyond Plan Mode, Claude Code has a few "modes" that control how much it checks with you before acting, from asking permission for anything risky, up to an auto-accept mode that just runs with things. If you are curious what mode you are in, just ask "what mode am I in, and what are my options?" The default is the safe, sensible starting point, so no need to change anything unless a mission tells you to.

That is the whole toolkit. Plain English, a `/` for commands, an `@` to point at files, `Esc` to stop it.

## Using AI responsibly

A couple of habits worth having from day one, on this course and on your real job:

- **You own the outcome.** Claude drafts and computes fast, but it can be confidently wrong. You are the one putting your name on the report, memo, or PRD, so skim what it produces and use `check my work` freely. If a number or quote looks off, it might be.
- **Never paste real secrets.** Do not type real passwords, API keys, or customer personal data into the chat, in this course or anywhere else. Treat it like any other tool that logs what you send it.

---

## The only 4 words you need to remember

Your mentor understands plain English, but these four shortcuts drive everything:

| Type this | What happens |
|-----------|--------------|
| `begin` | Start (or re-open) your current mission |
| `hint` | Get one nudge. Stuck again? Type it again for a bigger nudge |
| `check my work` | Your mentor reviews what you made and tells you if it passes |
| `next` | Mark the mission done and move to the next one |

Other useful things to say: `i'm stuck`, `explain that`, `what mission am I on?`, or literally any question. Talk to it like a patient colleague.

---

## What you will walk away with

- A real, reusable AI agent you built yourself (status reports, exec updates, or Jira stories — your choice).
- A market research brief, a data-insights report, a decision memo, a prioritized backlog, and a full PRD.
- A working landing page for your product, optionally live on a public URL.
- The confidence to use Claude Code on your actual job on Monday.

Now go open your terminal, run `claude`, and type `begin`. Your mentor is waiting.

---

## Who built this

This bootcamp was built by **Andrew Tomin**, a Senior/Staff Product Manager with 14+ years in enterprise B2B product. He builds AI agents and tools for his own workflows and teaches other knowledge workers (PMs, BAs, designers, founders, marketers) to do the same. The whole idea here: you learn Claude Code by doing real product work, not by watching slides.

Found a rough edge, or want to share what you built? That feedback is what makes the next version better.
