# Mission 7D - Optional: A Telegram Bot That Delivers the Report

> Mentor: optional bonus, about 40 minutes, needs 7C done. It needs a personal Telegram account and a phone or desktop app. It is fully optional: if the learner has no Telegram or does not want a bot, record "7D skipped by choice" under "Notes from your mentor" in `PROGRESS.md`, tick the box, and move on without any pressure. Hard rules for you: never ask the learner to paste the bot token (or any key) into the chat; never write the token into any file; if one appears in the chat anyway, tell them to revoke it in BotFather (`/revoke`) and issue a new one. The bot is read-only and answers only its owner.

## Goal

Create your own Telegram bot that, when you send it a command, replies with the latest report from 7C. Optionally it also looks up words in the Corvane policies from 6A, read-only. Save the code and a short how-to in `workspace/work/telegram-bot/`.

## Why it matters

A report in a folder still needs you to open the folder. A message on your phone arrives by itself. A bot is also a first taste of what an agent is: a small program that waits for a message and answers by rules you set. A bot is like a clerk at a counter: it receives messages and replies following the rules you give it.

Plain words for the terms:

- **Bot:** a small program with a Telegram address. People write to it, it replies.
- **BotFather:** the official Telegram bot that creates other bots for you.
- **Token:** a long string BotFather gives you. It is the bot's password. Whoever has it can control the bot.
- **Environment variable:** a named setting kept by your computer outside your project files (you met it in 3C). The program reads it when it starts, and the secret never sits in a file you might share.
- **Chat id:** the number that identifies your Telegram chat. The bot uses it to check "is this message from my owner?".

## What to do

Skip is fine at any point. Say "skip 7D" and your mentor records it.

1. **Create the bot.** On your phone or the Telegram desktop app, find the official **@BotFather**, send `/newbot`, pick a name and a username that ends in `bot`. BotFather replies with a token. Do not paste it here. Do not copy it into any file. Do not screenshot it.
2. **Keep the token as an environment variable.** Open a normal terminal window (not this chat). On Mac or Linux type `export TELEGRAM_BOT_TOKEN=` followed by your token, then Enter. On Windows PowerShell use `$env:TELEGRAM_BOT_TOKEN = "your token"`. That keeps it for this terminal window only, which is enough for today and means nothing is saved anywhere. Same rule as in 3C: never in a file, never in a chat. Optional, for later: a `.env` file that is listed in `.gitignore` so it is never shared (ask the agent to set it up, and ask it never to print the file).
3. **Ask the agent to build the bot.** The agent does not need your token to write code; it only needs to know the variable's name:
   > "I am not technical. Build a tiny Telegram bot in workspace/work/telegram-bot/. It must read the token from the environment variable TELEGRAM_BOT_TOKEN and never contain or print the token. Use only what is already on my computer (check what I have first; if Python is there, use it, and avoid installing extra packages if you can). Commands: /start replies with a greeting and the list of commands; /report replies with the contents of workspace/work/proactive/cr-weekly-report.md (if the file is missing, say so). The bot only reads files, it never writes or deletes anything. Explain every step in plain words."
4. **Add the owner check.** The bot must answer only you:
   > "Add this rule: the bot reads my chat id from the environment variable TELEGRAM_OWNER_ID. A message from any other chat gets no reply at all. For the first run, if TELEGRAM_OWNER_ID is not set, the bot must reply to nobody and only print (in the terminal, not in Telegram) the chat id of the sender, so that I can copy it. Never log message contents."
   Start the bot in your terminal, write it any message from your Telegram, and read your chat id in the terminal. Stop the bot. Set `TELEGRAM_OWNER_ID` the same way as the token, and start it again.
5. **Test it.** From your Telegram send `/start`, then `/report`. You should receive the report from 7C. Then test the lock: ask a colleague or a second account to message the bot. It must stay silent. If you have no second account, ask the agent to explain how the check works, and ask it to point at the line in the code.
6. **Optional read-only policy lookup.** Ask the agent to add a command `/policy word` that searches the files in `data/corvane/s6/policies/` for the word and replies with the file name, section, and matching line, or "Not found in the sources". It is a plain search, with no AI and no key. Connecting a real AI model to a bot needs a provider key that costs money; do not do that in this mission.
7. **Write the how-to.** Ask the agent to create `workspace/work/telegram-bot/README-for-me.md`: how to start the bot (open a terminal, set the two variables, one command), how to stop it (Ctrl+C in that terminal), what it does and does not do, what to do if the token leaks (BotFather, `/revoke`, new token, set it again), and that the bot only runs while the computer and the terminal window stay open.
8. **Where it could live later.** Read, without buying anything, the guide [How to buy your own server and publish your work on it](https://aisandboxlab.com/assets/materials/own-server-en). A bot on your own computer answers only while the computer is on. A small rented server keeps it running all the time. You do not need one for this mission. Write one sentence in the how-to about whether you would ever want that, and why.

## Definition of Done

Either:

- `workspace/work/telegram-bot/` contains the bot code and `README-for-me.md`.
- The code reads the token from an environment variable, and the token appears nowhere in the folder (the learner or mentor searches the folder for the start of the token to confirm; the mentor does not ask to see the token).
- The learner received the 7C report in Telegram from `/report`.
- The bot ignores chats other than the owner's, and the learner can point at the check in the code.
- The how-to says how to start, stop, and what to do if the token leaks.

Or (skip path):

- The learner said "skip" and `PROGRESS.md` has a "7D skipped by choice" line under "Notes from your mentor".

## Hints (mentor: one at a time)

1. If the learner is about to paste the token into the chat, stop them: "Keep it in your terminal. The agent only needs the variable's name."
2. If the bot does not answer, ask: is the terminal window still open, and is the bot still running in it? Is the variable set in that same window?
3. If another person can chat with the bot and get a reply, ask: where in the code is the owner id compared?

## What you just learned

A bot is a small program that waits for a message and answers by rules you wrote. It can deliver the report from 7C without you opening a folder. You also practised the three habits that keep a bot safe: the token stays outside your files and chat, the bot answers only its owner, and it only reads.

**Bring it to your job:** list the one question people ask you every week that a read-only bot could answer from a document, and write it down as the first command.

## Mentor reference

Pass if the learner shows the working `/report` reply in their Telegram (a screenshot or reading the message aloud is fine, with no token visible), and the following hold:

- The code reads `TELEGRAM_BOT_TOKEN` and `TELEGRAM_OWNER_ID` from the environment. A search of `workspace/work/telegram-bot/` finds no token. A real token looks like a number, a colon, and a long string; if you spot one, the learner must revoke it in BotFather (`/revoke`) and set a new one.
- Non-owner messages get no reply. The code compares the sender's chat id with the owner id before doing anything.
- The bot only reads: no writing, deleting, or running of shell commands on behalf of a chat message.
- No message contents are logged. `.env` files, if any, are listed in `.gitignore`.
- `README-for-me.md` explains start, stop, and token leak steps in plain words.

If `/policy` was added, check that an unanswerable word gives "Not found in the sources", and that every answer names the file.

Common problems: the variable was set in a different terminal window than the one running the bot; two copies of the bot running at once (Telegram then rejects one of them; stop the extra one); no Python on the computer (let the agent pick another tool that is already installed, or skip).

Skip path: accepted without questions. The reason is not needed. Tick the box and record "7D skipped by choice".

This mission does not require the learner to buy a server, add an AI key, or pay for anything. If the learner wants a smarter bot later (free-form answers), they connect an AI provider key, set a spending limit in the provider's dashboard, and keep the key in an environment variable in the same way as the token.
