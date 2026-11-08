# Quick Guide - Install Claude Code (5-10 minutes)

You need Claude Code installed before the bootcamp will work. This guide gets you there from zero. No coding background needed. If you already have it, skip to [START-HERE.md](START-HERE.md).

> The official install page is always the source of truth: https://docs.claude.com/claude-code . If a command below ever looks different there, trust the docs.

---

## What you're installing (in plain words)

Claude Code is an AI assistant that lives on your computer and can read, write, and change files when you ask it in plain English. It runs in a "terminal" (a text window where you type commands) but you barely touch the terminal after setup - you just talk to the assistant.

You need two things:
1. **A Claude account.** A paid plan (Claude Pro or Max) or API access. A free account is not enough to run Claude Code.
2. **Claude Code itself**, installed with one command below.

---

## Step 1 - Open your terminal

- **Mac:** press `Cmd + Space`, type `Terminal`, press Enter.
- **Windows:** press the Start button, type `PowerShell`, press Enter. (If you have WSL/Ubuntu installed, you can use that instead, but PowerShell is fine.)

A window with a blinking cursor opens. That is the terminal. You type a line, press Enter, it runs. That is all.

---

## Step 2 - Install Claude Code (one command)

Copy the line for your system, paste it into the terminal, press Enter. This is the native installer, so you do **not** need to install anything else first.

**Mac (or Linux / WSL):**

```sh
curl -fsSL https://claude.ai/install.sh | bash
```

**Windows (PowerShell):**

```powershell
irm https://claude.ai/install.ps1 | iex
```

It will download and set itself up. This takes a minute or two. Some scary-looking text scrolling by is normal - it is just the installer talking to itself.

> Prefer the Node/npm route, or the command above did not work? If you have Node.js installed you can instead run `npm install -g @anthropic-ai/claude-code`. If you have neither and the installer failed, the docs page has every option: https://docs.claude.com/claude-code

---

## Step 3 - Start it and sign in (once)

In the same terminal, type:

```sh
claude
```

The first time, it walks you through signing in with your Claude account (it opens your browser - log in, approve, come back). You only do this once. After that, `claude` just starts.

If you see Claude greet you and wait for input, you are done. Type `/exit` to close it for now.

> **"command not found: claude"?** The terminal needs to be reopened so it sees the new install. Close the terminal window completely, open a fresh one, and type `claude` again. On Windows, do the same with a new PowerShell window.

---

## Step 4 (optional) - Use it inside VS Code or the Claude app

The terminal always works, but you have options. Pick whatever feels comfy:

- **VS Code:** install the **Claude Code** extension from the Extensions panel, then open your folder and start Claude from the side panel.
- **Claude Desktop app:** open the desktop app and start a Claude Code session there.

You do not need these to do the bootcamp. They are just nicer windows for the same tool.

---

## You're ready

Claude Code is installed and signed in. Now go to [START-HERE.md](START-HERE.md), unzip the bootcamp folder, open it with Claude Code, and type `begin`.

Stuck on any step? That is exactly what the **AI Sandbox Lab** community is for - drop your error there and someone will unstick you.
