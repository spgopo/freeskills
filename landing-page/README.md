# Landing Page

A one-page site whose only job is to get you an email or a booking — headline, three proof points, one form, one button, and an FAQ that kills the biggest objection.

The spine of this skill is **the One Job Rule**: a page that asks for two things gets neither. No nav bar, no social icons, no second offer. Everything that doesn't push toward the single action comes off the page. It also wires the form to a free service so the emails actually reach your inbox instead of disappearing.

## Install

1. Copy the `landing-page` folder into your Claude Code skills directory:
   ```bash
   cp -r landing-page ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/landing-page`.

## How to use

Run `/personalize` first so the page sounds like you. Then type `/landing-page` and say what you want people to do — join a list, grab a free guide, book a call.

It asks who it's for, what the one outcome is, three real proof points, and the biggest reason someone would close the tab. Then it writes the copy, builds one self-contained `index.html`, and shows you the page so you can react to it in plain words. You get a working file at `~/sites/<your-project>/index.html`. Run `/deploy-it` to put it on a real link.
