# First Product

Turn what you already know into one finished digital guide you can sell, written end to end in a single sitting.

Most people never sell anything because they're waiting to build the big thing. **A first product is small on purpose.** One guide, one reader, one result, sold for a small price. This skill interviews you about your angle and your lessons, then writes the actual 20 to 40 pages, not an outline of them.

## Install

1. Copy the `first-product` folder into your Claude Code skills directory:
   ```bash
   cp -r first-product ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/first-product`.

## How to use

Run `/personalize` once first so it knows your niche, audience, and offer. Then type `/first-product`.

It asks four questions: your angle, the three to five things you'd teach someone from scratch, a writing sample so it sounds like you, and what you want to charge. It shows you a chapter list, you say yes, and then it writes the whole guide.

You end up with two files in `~/guides/<your-guide>/`. `guide.md` is the guide itself, formatted so it converts to a PDF cleanly. `listing.md` is the copy for your product page (title, pitch, price, three bullets) plus an honest checklist of the handful of things you still have to do yourself, like making the storefront account and uploading the file.
