# Meeting Notes

Paste a meeting transcript, get back a clean markdown summary with every action item assigned to a person.

Most notes tools hand you a wall of text you never read again. This one pulls out only what someone who missed the call would need: what was decided, who owes what, and what's still open. The rule that keeps it useful: **decisions and action items are not the same thing.** Decisions are outcomes. Action items are tasks with an owner's name on them.

## Install

1. Copy the `meeting-notes` folder into your Claude Code skills directory:
   ```bash
   cp -r meeting-notes ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/meeting-notes`.

## How to use

Type `/meeting-notes` and paste your transcript. It works with output from any tool — Fireflies, Otter, Granola, Zoom. You get a file in `~/meeting-notes/` named by date and topic, with a short summary, the decisions, action items grouped by person, open questions, and next steps. Anything it can't confidently assign gets flagged so you can fix it rather than trusting a guess.

No setup needed. Install it and paste.
