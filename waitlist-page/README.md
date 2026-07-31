# Waitlist Page

A one-page "coming soon" that collects emails tonight, so you find out if anyone wants the thing before you spend three months building it.

The expensive mistake is building first and asking later. Twenty people who typed their email address is real information. Twelve friends saying "cool idea" is not. This builds one page with **one promise, one field, one button, and an honest date** — plus a real free place for the emails to land, so they don't disappear.

## Install

1. Copy the `waitlist-page` folder into your Claude Code skills directory:
   ```bash
   cp -r waitlist-page ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/waitlist-page`.

## How to use

Run `/personalize` first so the page sounds like you. Then type `/waitlist-page` and answer four questions: what the thing is, who it's for, what it gets them, and when it'll honestly be ready.

You pick a promise line from three options and pick where the emails land (Google Form, Formspree free tier, or a plain mailto). You get a finished page at `~/sites/<name>-waitlist/index.html` plus a notes file with your decision rule — how many signups means build it, and how few means don't.
