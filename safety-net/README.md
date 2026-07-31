# Safety Net

Set up your two undo systems so you can experiment without worrying you'll wreck your project.

Beginners build timidly because they think one bad prompt ruins everything. You actually have two separate undos: `/rewind` for instant undo of the last move, and Git checkpoints for permanent saves you can return to days later. **Rewind undoes moves, checkpoints save days.** This skill sets both up on the project you have open right now, makes your first real checkpoint, and leaves a one-page cheat sheet.

## Install

1. Copy the `safety-net` folder into your Claude Code skills directory:
   ```bash
   cp -r safety-net ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/safety-net`.

## How to use

No setup needed. Type `/safety-net` and say which project you're working on. It has you test `/rewind` once on a throwaway change so the fear goes away, checks whether Git is on the project and sets it up if not, then makes your first named checkpoint for you. You never type a Git command — you say a sentence, Claude runs it.

You get `~/claude-safety-net.md`: a one-page cheat sheet with the exact recovery scripts for "I broke it", "go back one step", and "go back to this morning", plus the move for keeping both versions when you want the old one back but don't want to lose what you've made since. Keep it open in a tab while you build.
