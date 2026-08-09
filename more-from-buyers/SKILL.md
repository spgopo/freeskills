---
name: more-from-buyers
description: Find 3 to 5 concrete ways to make more money from the customers you already have, without more traffic, more followers, or a bigger audience. Looks at the one thing you sell now and ranks the moves by effort, easiest money first. Use when the user says "how do I make more money from what I have", "audit my offer", "I'm leaving money on the table", "should I raise my price", "add an upsell", "how do I add recurring revenue", "my offer only makes money once", or "/more-from-buyers".
---

# More From Buyers: the money is behind the sale

Most people who want more revenue go looking for more people, so they push harder on posts and traffic. That's the expensive way. The cheaper money is usually sitting behind a sale you're already making: a price that's too low, a small add-on nobody offered, a next step nobody pitched.

This skill looks at the one thing you sell today and hands you 3 to 5 specific moves, ranked so the easiest money comes first.

## Read this before you run it
This skill needs an offer that's already selling. It doesn't take many. A handful of sales is plenty. It works off what real buyers actually did, so without any sales there's nothing to audit and it would just make things up.

Check that with the user in the first message. If they haven't sold anything yet, tell them plainly and send them to the right place instead:
- No offer written down yet, or they can't say it in one sentence: run **offer-builder** first.
- Offer exists but they don't know what to charge: run **pricing-calculator** first.

Both are free and in this repo. Say it kindly and without making it a failure. Getting the first sale is a different job than getting more from the buyer, and doing them in the wrong order wastes a night.

## Personalization
This skill works in *your* brand voice. Before running, load the brand profile at `~/.claude/brand-profile.md`.
- If it doesn't exist, run the **personalize** skill first (or just tell me your name, niche, offer, and audience, and I'll create it).
- If a field this skill needs is blank, I'll ask one or two quick questions and save the answers back to the profile so you only answer once.
- Never invent facts or results about the user. Use only what's in the profile, or ask.

## Steps

### 1. Get the current picture
Ask these six. Keep it conversational and don't dump all six at once if the user is answering in full sentences.

1. What do you sell, and what do you charge? (the one main thing)
2. Is it a one-time payment, or does it bill every month?
3. Roughly how many do you sell a month? If it's monthly, do people stay or drop off?
4. What happens right after someone buys? Do you offer them anything else, or nothing?
5. When someone says no, what do they usually say? ("too expensive", "not right now", "I'd rather you just do it for me")
6. What does the buyer actually get out of it, and what's that worth to them in money or hours saved?

Answer 6 is the one people skip and it's the one that decides the price move. Push for a real number or a real amount of time.

### 2. Say the current model back in one line
Something like: "One-time $300 audit, about 15 a month, nothing offered after, so roughly $4,500 a month." Get them to confirm it. If they can't confirm the numbers, use ranges and say they're rough.

### 3. Run the offer through the six levers
Take each one and decide whether it's a real opportunity for *this* offer. Skip the ones that don't fit. Forcing all six is how you end up with generic advice.

- **Raise the price.** If the outcome is worth far more than they charge, the price is too low. The signals: nobody ever pushes back on price, almost everyone says yes, buyers seem thrilled. Propose a specific new number and the reason it's justified.
- **Order bump.** A small cheap add-on offered at the moment of payment. "Add X for $Y?" Think of what naturally rides along with the main thing. It's low effort and almost pure profit.
- **Upsell.** A bigger related offer shown right after they buy, while trust is at its highest. "You've got X. Want me to do Z too, or just handle it for you?" What's the obvious level up?
- **Downsell.** A smaller or cheaper version for people who wanted in but the yes was too big. A payment plan counts. This turns some no's into smaller yeses instead of nothing.
- **Something recurring.** Turn a one-time sale into money that comes every month: a support plan, ongoing check-ins, a monthly membership, or a set fee every month for staying available. For a one-time offer this is usually the biggest lever there is.
- **Keep buyers longer.** Only if they already bill monthly. People leaving is cheaper to fix than finding new people. Use their answers to 3 and 5 and propose one concrete fix, like a better first week or one quick early win.

### 4. Pick the 3 to 5 strongest and make each one specific
For each move, say exactly what to add, roughly what to charge, and the one line they'd use to pitch it. "Add an upsell" is not a move. "After the audit, offer the fix itself for $1,500" is a move.

### 5. Rank by effort, easiest money first
Sort them into three buckets so they know what to do tonight versus what waits:

- **This week.** Usually the price change, the order bump, the downsell. These are mostly a decision plus one sentence, with nothing to build.
- **This month.** The upsell, or a simple recurring add-on.
- **This quarter.** A full membership or monthly-fee layer, a premium tier, a system for keeping people.

For each move write: the move, how to implement it, the likely impact, and the effort level.

On impact, be directional and honest. "Roughly 20 to 30% more on every sale" is fine. A precise made-up figure is not. Never state what a change will earn as a fact.

### 6. Add a premium tier if it fits
A done-for-you or VIP version at a much higher price. Even if almost nobody buys it, it makes the main offer look reasonable next to it, and it catches the buyers who want the best. Sketch what's in it and a price.

### 7. Check they can actually deliver it
Before you hand the list over, look at it as a workload. If two of the moves would bury them in delivery work they can't do, say so and mark which one to do first. Money that wrecks delivery costs more than it makes.

## Save the output
Write the audit to `~/offers/more-from-buyers-<offer-slug>-<YYYY-MM-DD>.md` (create `~/offers/` if needed). The date is in the name on purpose, so re-running this in a few months doesn't paint over the last one.

The file contains: the current model in one line, the ranked moves with implementation, impact and effort for each, the premium tier idea, and any delivery warning from step 7.

Tell them the path, then give one next action: do the top "this week" move this week. Offer to write the actual wording for whichever move they pick, the bump line, the upsell pitch, or the downsell email.

## Example (input → output)
**Input:** "I sell a $300 one-time website audit to small online shops. About 15 a month. After they buy I don't offer anything. People who say no usually say they'd rather I just fix the stuff myself. The audit normally finds problems costing them thousands in lost sales."

**Output (excerpt, saved to `~/offers/more-from-buyers-website-audit-2026-08-08.md`):**

> **Current model:** One-time $300 audit, about 15 a month, nothing offered after, roughly $4,500 a month.
>
> **1. Raise the price to $500. This week.**
> You find thousands in lost sales for $300 and nobody pushes back. Impact: about $3,000 more a month at the same volume. Effort: change one number.
>
> **2. Offer the fix itself at $1,500. This week.**
> Your no's are literally asking for this. Offer it to everyone, whether they take the audit or pass on it. Impact: even 3 a month is another $4,500. Effort: write one offer.
>
> **3. Order bump: 48-hour turnaround for $100. This week.**
> One checkbox at checkout. Impact: close to pure profit on maybe a third of buyers. Effort: one line.
>
> **4. Monthly monitoring at $200 a month. This month.**
> Ongoing checks after the fix. Turns a one-time buyer into money every month. Impact: the biggest long-term lever here. Effort: decide what you send them each month.
>
> **Premium tier:** Full teardown plus 90 days of working together at $4,000. Makes the $500 audit look small and catches the shops who want it handled end to end.

## Notes / edge cases
- The whole point is getting more out of the customers you already have. If the user's instinct is "I need more traffic", bring them back here first. Selling more to people who already bought is cheaper than finding new people.
- Don't force all six levers. Three moves that fit this offer beat six that fit any offer.
- Price is their call. Recommend a number and the reasoning, then let them set it.
- If they sell to businesses, the price lever is usually bigger than they think. If they sell to individuals, the recurring lever usually is.
- If they've sold fewer than about five, run it anyway but keep the moves to price and one add-on. There isn't enough of a pattern yet to build a whole set of extra offers on.
- Come back to this every few months. The right move at 15 sales a month isn't the right move at 50.
