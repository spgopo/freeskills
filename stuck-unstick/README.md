# Stuck / Unstick

Claude keeps giving you the wrong thing and you're going in circles. This gets you out.

There are five traps beginners fall into, and every one has a specific way out: the ask was too big, you're describing the fix instead of what you saw, the chat is polluted after 40 messages, you changed three things at once, or you're trying to edit code by hand. This skill names the trap and **hands you the exact sentence to send next** — written for you, ready to copy.

## Install

1. Copy the `stuck-unstick` folder into your Claude Code skills directory:
   ```bash
   cp -r stuck-unstick ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/stuck-unstick`.

## How to use

No setup needed. Type `/stuck-unstick` when you're stuck. It asks two questions — what you asked for, and what you got instead — then names which trap you're in and writes your next message for you.

You get the diagnosis and the sentence saved to `~/build-log.md`, plus explicit permission to `/rewind` and restart clean if two more tries don't land. Restarting a piece of work is cheap. Fighting a broken direction for three nights is not.
