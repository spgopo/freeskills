# Caption Writer

Turn something you built into a caption you can paste and post, in your own voice.

Most people finish a thing and then say nothing, because posting feels like bragging. This skill fixes that by picking one of four post shapes that reliably work — showing the thing, the lesson from a mistake, the before/after, or the honest progress update — and writing a first line that does all the work. **Show the thing, don't announce yourself.**

## Install

1. Copy the `caption-writer` folder into your Claude Code skills directory:
   ```bash
   cp -r caption-writer ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/caption-writer`.

## How to use

Run `/personalize` once first so the skill knows your voice and audience. Then type `/caption-writer` and describe what you made, however messy — a link, a screenshot, or just "I built this thing that does X."

It asks which platform you're posting on, picks the post shape, writes three first lines and tells you which one it would use, then hands you the finished caption sized for Instagram, LinkedIn, X, or TikTok. If there's a link, it ends with a comment keyword instead of a raw URL, because comments turn into conversations. The caption is saved to `~/captions/`.
