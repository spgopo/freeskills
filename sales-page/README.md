# Sales Page

A page that looks like a real product and actually sells it — built in the order that makes people buy, not the order you feel like writing it in.

Most first sales pages fail on sequence. They open with the product, name the price before anyone wants the outcome, and bury the proof at the bottom. This one runs problem → after-state → what it is → what's included → proof → price → guarantee → FAQ, with **one button repeated three times** and the price said exactly once. The rule underneath all of it: never put price before value.

## Install

1. Copy the `sales-page` folder into your Claude Code skills directory:
   ```bash
   cp -r sales-page ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/sales-page`.

## How to use

Run `/personalize` first so the page sounds like you. Then type `/sales-page` and describe what you're selling.

It checks you have a real price and a real offer first — if not it sends you to `/pricing-calculator` or `/offer-builder` and waits. Then it asks about the problem people feel, what's included, what proof you actually have, and the three reasons someone would say no. It writes the copy, builds one self-contained `index.html`, and has you read it out loud to catch the cringe.

You get a file at `~/sites/<your-project>/index.html`. Run `/deploy-it` to publish it, then send the link to three people who already said they were interested.
