# Error Decoder

Paste the red text. Get back what broke in plain English and the exact sentence to paste to Claude to fix it.

Red text stops beginners cold, and a lot of it doesn't even need fixing. This skill sorts every error into one of four buckets — **Noise, Cosmetic, Blocked, or Rewind it** — translates it into kitchen-table English, and hands you one copy-ready sentence to send back to Claude. You never open a file or edit a line of code.

## Install

1. Copy the `error-decoder` folder into your Claude Code skills directory:
   ```bash
   cp -r error-decoder ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/error-decoder`.

## How to use

No setup needed. Type `/error-decoder` and paste whatever scared you — an error, a wall of red, a message you don't understand. It asks two things: what you'd just asked Claude to do, and whether the thing still runs.

You get how bad it is, what broke and why, what it definitely did NOT do to your files, and the fix sentence to paste. It saves to `~/claude-errors/` with the date, so the folder slowly becomes your own troubleshooting log. If things get tangled, it tells you to use `/rewind` instead of debugging — undoing is faster than untangling.
