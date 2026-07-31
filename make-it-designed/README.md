# Make It Designed

Point it at a page you already built and it turns "works but looks default" into "looks designed" — without rebuilding anything.

Most people try to fix an ugly page by adding: another color, another section, another icon. That's the cause, not the cure. This skill **removes three things before it adds one**, runs a fixed checklist on type, spacing, color, and hierarchy, then adds exactly one signature detail so the page has a point of view.

## Install

1. Copy the `make-it-designed` folder into your Claude Code skills directory:
   ```bash
   cp -r make-it-designed ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/make-it-designed`.

## How to use

No setup needed. Type `/make-it-designed` and give it the path to your page. It reads the file, shows you what it's cutting and why, fixes the font pairing and size jumps, snaps every gap to a real spacing scale, cuts the palette down to five colors, and adds one signature touch — a hand-drawn underline, an editorial headline, or a stat band.

Your content and links never move. If you hate it, type `/rewind`. It also writes a short change log to `~/design-notes/` so you can see what changed.
