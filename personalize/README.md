# Personalize

Answer a handful of questions once, and every other skill in this pack writes in your voice, for your offer, to your audience.

Run this one first. It's the setup step the other skills depend on. All it does is interview you and save the answers to one file at `~/.claude/brand-profile.md`. After that, **you never have to explain yourself again.** Every skill reads that file automatically instead of asking who you are and what you sell.

## Install

1. Copy the `personalize` folder into your Claude Code skills directory:
   ```bash
   cp -r personalize ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/personalize`.

## How to use

Type `/personalize`. It asks five small groups of questions: your name and what you do, who you're trying to reach, what you sell, how you like to sound, and any real proof or links you have. Short answers are fine. Skip anything you don't have yet.

It then writes `~/.claude/brand-profile.md` and tells you the path. It won't make up results, revenue, or credentials. Blanks stay blank until you fill them in. Run `/personalize` again anytime to update a section.
