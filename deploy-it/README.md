# Deploy It

Take whatever you just built and put it on a real public web address, free, in about ten minutes.

Until it has a link, the thing you made doesn't quite count — nobody can open it. This skill walks Vercel sign-in one click at a time, explains the GitHub step in plain English instead of jargon, and fixes the three things that actually break for beginners. The whole idea is that **ugly but live beats pretty but local**: the rep isn't the polish, it's sending the link to a real person.

## Install

1. Copy the `deploy-it` folder into your Claude Code skills directory:
   ```bash
   cp -r deploy-it ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/deploy-it`.

## How to use

No setup needed. Build something first with `/first-website`, `/landing-page`, `/link-in-bio`, `/sales-page`, or `/simple-game`, then type `/deploy-it`.

It finds what you built, sets up the GitHub side for you, and gives you the Vercel steps one at a time — you click, it waits. No card, no code, no reading error logs. If the page comes up blank or the repo won't show in the list, it already knows those and fixes them.

You end with a live `.vercel.app` link, and it gets appended to `~/my-links.md` so you build up a list of everything you've shipped. Then open it on your phone and send the link to one person today.
