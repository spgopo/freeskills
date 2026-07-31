# Design Taste

Name 1-3 sites you love, get back a written design system you can point every future build at.

Taste isn't a gift, it's a set of decisions somebody wrote down. This skill pulls the real decisions out of sites you already like — hex codes, font pairing, size jumps, spacing steps — and saves them to one file. **Decide once, then stop re-deciding.** Every build after this reads that file, so your pages start looking like they came from the same person.

## Install

1. Copy the `design-taste` folder into your Claude Code skills directory:
   ```bash
   cp -r design-taste ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/design-taste`.

## How to use

No setup needed. Type `/design-taste` and name or paste 1-3 sites you like the look of, plus one sentence about how you want people to feel. If you can't name any, it gives you six directions to pick from.

You get back two files: `~/.claude/design.md` with the palette, fonts, scale, spacing, and a don't-do list, and a preview page you open in your browser to actually see it. After that, start any build prompt with "Read ~/.claude/design.md and follow it."
