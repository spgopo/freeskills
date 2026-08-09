# Proposal Writer

Messy notes from a call go in. A clean, ready-to-send proposal comes out, saved as a file you can paste straight into an email.

A proposal isn't a price list with your name on it. It's a short document that proves you understood the problem, shows what changes when it's fixed, and puts the price after the buyer already wants the thing. **Value first, number second.** Get that order right and the price stops being the scary part.

## Install

1. Copy the `proposal-writer` folder into your Claude Code skills directory:
   ```bash
   cp -r proposal-writer ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/proposal-writer`.

## How to use

Run `/personalize` once first so it writes in your voice. Then type `/proposal-writer` and paste whatever you've got from the call. Rough bullets are fine.

It pulls out the three things it can't write without (their problem, what you're delivering, your price) and asks if any are missing. It won't guess a number and it won't invent scope. Then it writes the document: their situation in their own words, the outcome, exactly what they get, the timeline, a two-option price table with one marked recommended, your guarantee if you have one, and a single clear next step instead of "let me know."

You end up with a file at `~/proposals/proposal-<client>-<date>.md`, plus a short email to send it with.
