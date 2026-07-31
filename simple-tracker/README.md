# Simple Tracker

A small personal tracker that runs in your browser and saves to your own machine — habits, workouts, clients, books, money in. One file, no login, no database, no monthly bill.

Most of what people want from an app is a list they can add to and one number that tells them how it's going. That doesn't need a backend. Every good small tracker is the same three parts: **one thing you add, one list you see, one number at the top.** Build those, use it for a week, then change the one thing that annoyed you.

## Install

1. Copy the `simple-tracker` folder into your Claude Code skills directory:
   ```bash
   cp -r simple-tracker ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/simple-tracker`.

## How to use

No setup needed. Type `/simple-tracker` and say what you want to track. If you're not sure, it gives you six ideas — habit tracker, workout log, client pipeline, reading list, money in, content log — each with a starter prompt.

You get a working file at `~/tools/<name>/index.html`. Bookmark it, or add it to your phone's home screen so it opens like an app. Your data saves in your browser, and the page includes export and import buttons so you can back it up and move it.
