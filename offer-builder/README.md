# Offer Builder

Turn "here's my product" into a written, ready-to-pitch offer that's hard to say no to.

This follows Alex Hormozi's Value Equation. People buy when the value feels high, and value goes up when the outcome is bigger and more believable, and down when it takes more time and more effort. So the whole build is about **stacking one deliverable against every real obstacle** your buyer has, then removing risk with a guarantee.

## Install

1. Copy the `offer-builder` folder into your Claude Code skills directory:
   ```bash
   cp -r offer-builder ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/offer-builder`.

## How to use

Type `/offer-builder`. It reads your brand profile at `~/.claude/brand-profile.md`, so run `/personalize` first if you haven't. Then it walks you through nine steps: name the dream outcome, list what stops people getting it, stack a deliverable against each obstacle, cut the time and effort, name the offer, write a guarantee, add true urgency, and add bonuses.

You get the finished offer saved to `~/offers/<offer-name>.md`, plus one sentence you can say on a call or put on a sales page.
