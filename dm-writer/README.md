# DM Writer

Get one short message to one real person, written in your voice, that starts a conversation instead of pitching at them.

A good DM isn't a broadcast. It's a message to *this* person, about *this* relationship, with one reason for reaching out. The rule the whole skill runs on: **lead with them.** The first line is about the person you're messaging, not your offer. One reason, one ask, and a question they can answer in a line.

## Install

1. Copy the `dm-writer` folder into your Claude Code skills directory:
   ```bash
   cp -r dm-writer ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/dm-writer`.

## How to use

Type `/dm-writer` and say who you're messaging. It asks three things: who they are, how well you know them, and what you want (start a conversation, share your offer, or follow up). Then it writes a 2–5 sentence message that matches how warm the relationship actually is, plus one follow-up line you can send if they go quiet. Everything gets saved to `~/dm-drafts.md` so you build your own swipe file.

It reads your brand profile at `~/.claude/brand-profile.md` to write in your voice. If you haven't set that up yet, run `/personalize` first.
