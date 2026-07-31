# Warm Outreach

Build a ranked list of people who already know you, plus a first message that starts a conversation instead of pitching a friend.

Your first customer almost never comes from a stranger. It comes from a past client, an old coworker, someone in a group you're already in, or the person who likes every post you make. The rule here is **warm before cold, honest before pushy.** You're not blasting anyone. You're talking to real people.

## Install

1. Copy the `warm-outreach` folder into your Claude Code skills directory:
   ```bash
   cp -r warm-outreach ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/warm-outreach`.

## How to use

Type `/warm-outreach`. It reads your brand profile at `~/.claude/brand-profile.md`, so run `/personalize` first if you haven't. It walks you bucket by bucket through everyone who knows you, aiming for 20 to 40 names, then scores each one on fit and warmth so you know who to message first and who to ask for a referral instead.

You get the ranked table and three opener variations (reconnect, soft signal, referral ask) saved to `~/warm-outreach-list.md`, each with a bracketed slot for the one personal detail you fill in per person. Send the top five this week, not the whole list.
