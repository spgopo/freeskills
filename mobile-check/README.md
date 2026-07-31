# Mobile Check

See the page you built the way a real person on a phone sees it, and get a numbered fix list you can paste straight back to Claude.

You build on a laptop. Most of your visitors are on a phone, one-handed, half-distracted. This checks the seven things that actually break at 375 pixels wide — sideways scroll, buttons too small to tap, tiny text, images blowing out the layout, a main button nobody can reach, and whether the page still reads with JavaScript off. **Every problem comes with the exact sentence to paste back**, because the beginner move is describing the symptom, not editing the code.

## Install

1. Copy the `mobile-check` folder into your Claude Code skills directory:
   ```bash
   cp -r mobile-check ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/mobile-check`.

## How to use

No setup needed. Type `/mobile-check` and give it the path to your page (or a live URL). It reads the whole thing at phone width and hands back a numbered list ordered by damage — page-killers first, cosmetic stuff last — plus a short list of what already passed.

Do them one at a time. Paste fix #1, look at the page, then come back for #2. The full report saves to `~/mobile-checks/`.
