# Thread Writer

Turn one idea into an X thread or a long LinkedIn post that people read all the way to the end.

Threads fail in the middle, when a line gives the reader permission to stop. This skill builds one where the hook makes a promise it actually keeps, a real number or moment shows up early so people trust you, and every line's only job is to pull them into the next one. **One idea per line. No stacking.**

## Install

1. Copy the `thread-writer` folder into your Claude Code skills directory:
   ```bash
   cp -r thread-writer ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/thread-writer`.

## How to use

Run `/personalize` once first so the skill writes in your voice. Then type `/thread-writer` and describe the idea, plus anything real you can point to — a number you measured, a night something broke, a before and after.

It compresses your idea to one sentence, writes three hooks and picks one, builds the body line by line, and gives you an ending that lands instead of trailing off. You get it formatted for X (numbered posts) or LinkedIn (one block), saved to `~/threads/`.
