# Decision Helper

You're stuck between options. This gets you to a decision today, not another list of pros and cons.

Being stuck is rarely about missing information. It's an unnamed constraint, or two things you want that can't both win. So this skill puts the options you *hadn't* listed on the table, makes you say what you're really optimizing for, drags out the thing you haven't admitted, and then **makes the call** — one recommendation, one reason, one first move.

## Install

1. Copy the `decision-helper` folder into your Claude Code skills directory:
   ```bash
   cp -r decision-helper ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/decision-helper`.

## How to use

No setup needed. Type `/decision-helper` and describe what you're stuck on, however messy — "I can't decide whether to quit" is enough to start.

It asks what winning looks like, digs for the constraint you haven't said out loud, then checks how hard the decision is to undo. Cheap to reverse means decide now and move. Hard to reverse means one specific check with a date on it. You end with a recommendation, what it costs you, what would prove it wrong, and one thing to do today. Saved to `~/decisions/`.
