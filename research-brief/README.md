# Research Brief

Turns "I need to understand X before Monday" into one page you can actually walk into a room with.

Not a reading list and not twenty open tabs. The answer sits in the first three lines, then the brief sorts everything into **what's settled, what's contested, and what nobody knows yet** — with every number carrying the date it came from, and anything that couldn't be checked marked unverified instead of guessed.

## Install

1. Copy the `research-brief` folder into your Claude Code skills directory:
   ```bash
   cp -r research-brief ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/research-brief`.

## How to use

No setup needed. Type `/research-brief` and say what you need to understand — "brief me on the four-day week, I've got a call Monday".

It asks one question: what you're doing with it. A brief for a purchase looks different from a brief for a meeting. Then it searches the web where it can, goes to primary sources rather than articles about them, and deliberately hunts for the strongest case against. You get a sourced one-pager saved to `~/research/`, ending with an honest list of what it couldn't confirm.
