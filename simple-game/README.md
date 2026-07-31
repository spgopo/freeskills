# Simple Game

Build a playable browser game in one sitting — one file, opens anywhere, works on a phone, nothing to install.

A game is the best first build because **you cannot lie to yourself about whether it works.** You press a key and the thing moves or it doesn't. People also actually play games — send someone a website and you get "nice," send them a game and you get their score back. And it's one self-contained file with no database, no login, and no server.

## Install

1. Copy the `simple-game` folder into your Claude Code skills directory:
   ```bash
   cp -r simple-game ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/simple-game`.

## How to use

No setup needed. Type `/simple-game` and you get a menu of about eight classics tagged by how long they take — 15 minutes, an hour, one evening. Pick one, or name a game you loved.

It writes a four-part spec with you first (container, one gameplay rule per bullet, UI placement, and "show me a live preview"), builds it, and opens it so you can play. You react in plain words for a few rounds until it feels right. Then it runs the "make it yours" pass: reskin it to something from your life, add exactly one twist, put your name on the title screen, save the high score, add a share button.

You get a playable file at `~/games/<your-game>/index.html`. Run `/deploy-it` to get a link and send it to three people tonight.
