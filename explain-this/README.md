# Explain This

Paste any file, folder, snippet, or config you don't recognize and get a plain-English explanation written for someone who has never coded.

Your project fills with files you never created, and it starts feeling like someone else's machine. This skill answers the five questions you actually have — what this is, what it does, why it's here, **what would happen if it vanished**, and which parts you'd ever realistically change — then closes with one thing worth understanding and one thing you have permission to ignore forever.

## Install

1. Copy the `explain-this` folder into your Claude Code skills directory:
   ```bash
   cp -r explain-this ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/explain-this`.

## How to use

No setup needed. Type `/explain-this` and paste whatever's confusing you, or just name the file and let it read it. A whole file, a folder listing, five lines, one word you saw — all fine. You don't need to ask a question; it assumes the question is "what is this and should I care."

You get the explanation saved to `~/claude-explained/`, which slowly becomes a glossary of your own project in your own words. Nothing to do afterward — this one is for reading.
