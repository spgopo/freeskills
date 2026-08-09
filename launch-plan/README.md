# Launch Plan

A day-by-day plan for launching the thing you built, sized to the audience you actually have.

A launch is a spike, not your engine. It takes the interest you've already built and concentrates it into a few days so the sales land together. This skill picks the launch type that fits your stage (pre-sell, waitlist, directory, or a limited-time deal), sets a real date and a real number, and tells you what to do each day. If your audience is basically none yet, it says so instead of promising you a spike that can't happen.

## Install

1. Copy the `launch-plan` folder into your Claude Code skills directory:
   ```bash
   cp -r launch-plan ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/launch-plan`.

## How to use

Run `/personalize` once first so it knows your offer, audience, and voice. Then type `/launch-plan` and tell it what you're launching.

It asks five questions, including how big your audience really is, then recommends one launch type and explains why that one. You get a plan saved to `~/launches/launch-<your-offer>-<date>.md` with the launch type, the date, the number you're aiming at, a checklist of what you still need to make, and a dated timeline from the first teaser through close day. It'll offer to draft the messages in your voice too.
