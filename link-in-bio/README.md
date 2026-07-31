# Link in Bio

Your own branded link page — photo, name, one-line pitch, and 4-6 buttons — built in an evening and better than the Linktree everyone else has.

The real skill here isn't the design, it's **the order of the links**. People tap one of the first two buttons and leave, so the thing that makes you money goes at the top and everything below button four is close to invisible. The skill sorts your links in front of you, cuts the list down, and rewrites every button label into a plain action.

## Install

1. Copy the `link-in-bio` folder into your Claude Code skills directory:
   ```bash
   cp -r link-in-bio ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/link-in-bio`.

## How to use

Run `/personalize` first so the page sounds and looks like you. Then type `/link-in-bio` and dump every link you'd want on there.

It asks for a photo, your name, and a one-line pitch, then sorts and cuts your links and explains each position. It builds one self-contained `index.html` designed phone-first, because that's where almost everyone opens it. Preview it at phone width, thumb-test the buttons, react in plain words. You get a file at `~/sites/<your-project>/index.html` — run `/deploy-it` to turn it into a real link for your bio.
