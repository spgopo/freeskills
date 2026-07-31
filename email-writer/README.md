# Email Writer

Writes the email you've been avoiding — the invoice chase, the no, the apology, the third follow-up.

Hard emails don't get sent because people can't find the tone, so they write four paragraphs of build-up and hide the real ask in the last line. This skill flips that: **one ask, near the top**, in short plain words that still sound like you.

## Install

1. Copy the `email-writer` folder into your Claude Code skills directory:
   ```bash
   cp -r email-writer ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/email-writer`.

## How to use

Run `/personalize` first so the email sounds like you. Then type `/email-writer` and describe the situation in your own words — "a client owes me money and I've already chased once" is enough.

It asks three things: who this person is to you, what you want to happen, and how blunt you can be. Then it hands you a subject line and a short body with the ask up top, plus a warmer and a firmer version of the riskiest line so you can dial the tone without rewriting. Everything gets saved to `~/emails/`.
