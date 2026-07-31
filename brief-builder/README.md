# Brief Builder

Describe what you want in your own messy words and get back a prompt sharp enough to paste straight into Claude.

Most bad output comes from a thin ask. This skill fills in the five parts a prompt needs to work — **CONTEXT, GOAL, CONSTRAINTS, FORMAT, DONE-WHEN** — and shows you the before and after so you see exactly what made the difference. It also gives you a one-sentence compressed version for the forty small asks you make every week.

## Install

1. Copy the `brief-builder` folder into your Claude Code skills directory:
   ```bash
   cp -r brief-builder ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/brief-builder`.

## How to use

No setup needed. Type `/brief-builder` and describe what you want built, however vague. It reads back the deliverable to confirm, asks only for the details that would actually change the answer, and fills any gaps with clearly-marked assumptions instead of interrogating you.

You get a copy-ready brief saved to `~/briefs/`, plus the compressed one-liner: "Given [context], do [goal], without [constraint], formatted as [format] — done when [done-when]." Paste the long version into a fresh Claude session. If the result is off, change one part of the brief and run it again.
