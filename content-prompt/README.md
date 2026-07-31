# Content Prompt Generator

Get one question worth answering on camera, plus five hooks and text overlays, so you can hit record without staring at a blank page.

Most short-form advice tells you to comment on what's trending. This does the opposite: **the trend is the door, your story is the room.** The skill finds a live tension in your niche, then matches it to something you actually lived — a mistake, a turning point, a result that surprised you — and builds the prompt around that.

## Install

1. Copy the `content-prompt` folder into your Claude Code skills directory:
   ```bash
   cp -r content-prompt ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/content-prompt`.

## How to use

It reads your brand profile at `~/.claude/brand-profile.md`, so run `/personalize` first if you haven't. That's where it gets your audience, your pain point, your real proof, and your tone.

Type `/content-prompt`. You get back one question, the story seed it pulls from, why it's timely, five hooks (each with its own text overlay), a pick of which hook to use, and a follow CTA. If your profile is thin on real moments, it asks you for one and saves it.
