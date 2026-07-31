# Rewrite Plain

Rewrites anything into plain, direct language someone busy understands on the first read.

Unclear writing usually isn't a vocabulary problem — it's hedging, or a three-sentence run-up before anyone says anything. This strips that out and leaves your meaning exactly where it was. **A clarity pass, not a rewrite of your argument**: same facts, same position, said so it lands.

## Install

1. Copy the `rewrite-plain` folder into your Claude Code skills directory:
   ```bash
   cp -r rewrite-plain ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/rewrite-plain`.

## How to use

Run `/personalize` first so the rewrite still sounds like you and not like a template. Then type `/rewrite-plain` and paste the text, or give it a file path. Works on emails, posts, bios, sales pages, docs.

It asks one question — who reads this and what should they do — then cuts the throat-clearing, the hedging, the passive dodges, and the corporate words that mean nothing. You get a clean paste-ready version, the word count before and after, and three to five before/after pairs from your own writing so you start catching the pattern yourself. Saved to `~/rewrites/`, with your original kept at the bottom.
