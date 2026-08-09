# More From Buyers

Three to five specific ways to make more money from the customers you already have, ranked so the easiest one is first.

Most people chasing more revenue go looking for more people to sell to. **The cheaper money is usually behind a sale you're already making**: a price that's too low, a small add-on nobody offered, an obvious next step nobody pitched. This looks at the one thing you sell today and finds it. It does need an offer that's already selling, though a handful of sales is enough. If you haven't sold anything yet it'll say so and point you at `/offer-builder` or `/pricing-calculator` instead of guessing.

## Install

1. Copy the `more-from-buyers` folder into your Claude Code skills directory:
   ```bash
   cp -r more-from-buyers ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/more-from-buyers`.

## How to use

Run `/personalize` once first so it knows your niche, offer, and audience. Then type `/more-from-buyers`.

It asks six questions about what you sell, what you charge, how many you sell, and what happens after someone buys. Then it runs your offer through six ways to earn more from the same buyer: raise the price, add a small bump at checkout, offer a bigger next step, catch the no's with a cheaper version, add something that bills monthly, and keep buyers longer. It only keeps the ones that genuinely fit you.

You get a file at `~/offers/more-from-buyers-<your-offer>-<date>.md` with each move written out, what to charge, the likely impact, and how much work it is. They're sorted into this week, this month, and this quarter, so you know what to do tonight.
