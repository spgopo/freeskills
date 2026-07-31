# Objection Handler

A cheat sheet of calm, honest answers to the pushback you actually hear — written for your offer, in your voice.

**An objection is not a rejection.** It's a real concern someone needs answered before they can say yes. Most people either fold instantly or get defensive, and both lose the sale. Every response here follows the same shape: acknowledge, reframe, give one true reason it holds up, then invite a small next step. Nothing invented, no pressure.

## Install

1. Copy the `objection-handler` folder into your Claude Code skills directory:
   ```bash
   cp -r objection-handler ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/objection-handler`.

## How to use

Type `/objection-handler`. It starts from the four everyone hears — too expensive, no time, let me think about it, does this work for someone like me — then asks which ones you actually get and what else comes up. You get a full response for each plus a one-line version short enough to send in a DM, a reminder to ask a question before you answer, and a warm way to exit when it's genuinely a no. It all saves to `~/objection-cheatsheet.md`.

It reads your brand profile at `~/.claude/brand-profile.md` to write in your voice. If you haven't set that up yet, run `/personalize` first.
