# CLAUDE.md Builder

Stop re-explaining your project every time you open Claude Code.

Claude starts every session blank. A `CLAUDE.md` file in your project folder gets read automatically at the start of every session, so your rules stick. The trick most people get wrong: **short beats complete.** It's a command center, not a life story — a bloated memory file buries the rules that actually matter.

## Install

1. Copy the `claude-md-builder` folder into your Claude Code skills directory:
   ```bash
   cp -r claude-md-builder ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/claude-md-builder`.

## How to use

No setup needed. Open Claude Code inside your project folder and type `/claude-md-builder`. It asks six questions — what the project is, the one thing it has to do, your always rules, your never rules, where files live, and how you want to be talked to. Then it cuts your answers down to under 40 lines and writes `CLAUDE.md` into that folder.

At the end it tells you how to prove it worked: start a fresh session and ask "what are my rules?" If Claude answers without you explaining anything, the memory is live.
