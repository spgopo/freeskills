# Session Wrap-Up

End your build session so reopening tomorrow takes five minutes, not thirty.

You build for 90 minutes, close the laptop, and come back two nights later with no idea where you were. Half the next session goes to remembering. This skill is the last ten minutes of the night: it checks what actually changed, sorts working from half-done, and writes **one line** telling tomorrow-you exactly where to pick up. One line, not a to-do list — three items means you read all three and start none.

## Install

1. Copy the `session-wrapup` folder into your Claude Code skills directory:
   ```bash
   cp -r session-wrapup ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/session-wrapup`.

## How to use

No setup needed. When you're done building for the night, type `/session-wrapup`. It looks at what changed in the project rather than asking you to remember, tells you plainly what's working and what's half-finished, and prompts you to save a checkpoint before you close.

It appends a dated entry to `~/build-log.md`. Tomorrow, open that file first, read the last entry, do the first move, and nothing else.
