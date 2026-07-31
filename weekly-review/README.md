# Weekly Review

A 20-minute Sunday reset that shows you what you actually shipped and picks the one thing for next week.

Nightly progress is invisible. You build in stolen hours, some nights go nowhere, and by Sunday it feels like you did nothing — which is the main reason people quit in month two. **Progress is weekly, not nightly.** This skill reads your build log for the real evidence, gets a specific reason for everything that stalled, and then forces a cut: you name the ONE result for next week, and you say out loud what you're dropping.

## Install

1. Copy the `weekly-review` folder into your Claude Code skills directory:
   ```bash
   cp -r weekly-review ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/weekly-review`.

## How to use

No setup needed. On Sunday, type `/weekly-review`. It reads `~/build-log.md` and your plan files so you don't have to remember the week, lists what shipped, digs into why the stalled things stalled, and makes you pick one thing and park the rest.

You get `~/weekly-review.md` with the week's wins, the one thing, two parked items, and three specific moves placed into the nights you actually have. Put those three in your calendar before you close the laptop.
