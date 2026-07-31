# YouTube Hook Generator

Hooks for your video, built on the Kallaway framework — each one scored, and the top three delivered as a matching visual, spoken, and text hook.

The idea behind it: people click for one of four things — money, time, health, or status. But say it straight and their BS detector fires. So the skill aims **one step away from the desire**, at a proxy people believe. "Automate the part of your work you hate" beats "make more money."

## Install

1. Copy the `hooks` folder into your Claude Code skills directory:
   ```bash
   cp -r hooks ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/hooks`.

## How to use

It reads your brand profile at `~/.claude/brand-profile.md`, so run `/personalize` first if you haven't. That's how the hooks sound like your audience instead of generic copy.

Type `/hooks` and your video topic, outline, or key points. If you only give a topic, it asks one question: what's the most surprising thing in this video? You get back the desire it mapped to, five hook variations, the top three fully built out with scores, and a straight recommendation on which to use.
