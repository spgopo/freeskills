# First Website

Build your first real website by describing what you want out loud — no code, no setup, one file that opens in your browser.

You are not learning to code here. You are learning to direct. The skill drags your idea from vague to **surgical** — who the visitor is, the one action you want, the feeling, the hard constraints — then builds a version you can look at and react to in normal words. Five to ten rounds of that is the whole workflow, not a sign you're doing it wrong.

## Install

1. Copy the `first-website` folder into your Claude Code skills directory:
   ```bash
   cp -r first-website ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/first-website`.

## How to use

No setup needed. Type `/first-website` and describe the site you want, however messy. It asks a few short questions, builds one self-contained `index.html`, opens it so you can see it, then asks "what's the first thing that bugs you?" You answer in plain English, it fixes, you look again.

You end up with a real file at `~/sites/<your-project>/index.html` plus a short notes file for tomorrow. Then run `/deploy-it` to get it on a real web address and send the link to one person today.
