# Quote Calculator

Build a small instant-quote widget for a service business — the buyer picks a few options, sees a price range in seconds, and leaves their details.

Service businesses lose leads at "call for a quote." People want a rough number before they pick up the phone. This builds the tool that gives it to them, in one self-contained HTML file with no backend and nothing to pay for. Two rules run the whole thing: **always show a range, never a single hard number**, and always capture the lead after the range, never before it.

## Install

1. Copy the `quote-calculator` folder into your Claude Code skills directory:
   ```bash
   cp -r quote-calculator ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/quote-calculator`.

## How to use

No setup needed. Type `/quote-calculator` and describe the business — movers, cleaners, lawn care, painters, junk removal, detailing. It walks you through the real pricing logic: the base, the three to five things that move the number, and the floor and ceiling.

You get a working page at `~/sites/<business>-quote/index.html` plus a pricing notes file, tested against three real past jobs. It also works as a first paid job: build one for a local business using their real prices and send them the link.
