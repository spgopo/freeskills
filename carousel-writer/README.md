# Carousel Writer

Get the exact words for every slide of a carousel, plus a note on what goes on each slide, ready to build in Canva or hand to Claude.

Carousels get saved and shared more than any other post, and most people kill them on slide one by writing a paragraph. This skill writes slide by slide with the fewest possible words, and treats slide 1 as its own job — because **it's the only slide most people will ever see.** It writes the words, not the images.

## Install

1. Copy the `carousel-writer` folder into your Claude Code skills directory:
   ```bash
   cp -r carousel-writer ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/carousel-writer`.

## How to use

Run `/personalize` once first so the slides sound like you. Then type `/carousel-writer` and say what the carousel is about and what someone should be able to do after swiping through it.

You get 7 to 10 slides, each with a short headline, an optional support line, and one line describing what goes on the slide. Slide 1 comes with three options. The last slide is the ask. It also hands you a copy-ready prompt for building the whole thing as a web page in a fresh Claude Code session. Everything saves to `~/carousels/`.
