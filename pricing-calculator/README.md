# Pricing Calculator

Get a price based on what the result is worth to your buyer, not on how long it took you to make.

Most people undercharge because they price on effort. "It only took me a weekend" is how a build that makes a client $20,000 ends up as a $300 job. The fix is to **put a dollar number on the outcome first**, then charge a confident fraction of it, so the buyer still gets an obvious return.

## Install

1. Copy the `pricing-calculator` folder into your Claude Code skills directory:
   ```bash
   cp -r pricing-calculator ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/pricing-calculator`.

## How to use

Type `/pricing-calculator`. It reads your brand profile at `~/.claude/brand-profile.md`, so run `/personalize` first if you haven't. It works out what your offer is worth to the buyer in money made, money saved, time saved, or pain avoided, sets a price from that number, builds good/better/best tiers, runs the price against the usual objections, and picks a payment structure.

You get the value math, a recommended price, the tier table, and a few lines you can say out loud on a call, saved to `~/offers/pricing.md`.
