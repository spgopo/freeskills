# Testimonial Ask

The exact message to send asking for a testimonial, plus the three questions that produce a quote worth using.

Two things go wrong: most people never ask, and the ones who do ask so vaguely they get "great to work with!" — which is warm, useless, and sells nothing. This skill picks the right moment, writes the ask, and includes the **draft-it-for-them version** where you write the quote and let them edit, which gets by far the highest reply rate.

## Install

1. Copy the `testimonial-ask` folder into your Claude Code skills directory:
   ```bash
   cp -r testimonial-ask ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/testimonial-ask`.

## How to use

Run `/personalize` once first. Then type `/testimonial-ask` and tell it who the client is, what you did, and the last good thing they said about it.

You get a short message ready to send in the thread you already use with them, the three questions that produce a real before-and-after quote, and rules for tidying a rambling reply into something clean without putting words in their mouth. It also writes the permission message, because a quote you can't publish is worth nothing. Everything saves to `~/testimonials/`.
