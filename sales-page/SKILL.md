---
name: sales-page
description: Build a page that looks like a real product and actually sells it — problem, after-state, what it is, what's included, proof, price said once, guarantee, FAQ, and one button repeated down the page. Puts everything in the order that makes people buy instead of the order you feel like writing it in. Use when the user says "/sales-page", "build me a sales page", "a page to sell my thing", "I need a page for my course", "write my sales page", "product page", "checkout page for my offer", "a page that sells", "how do I sell this online", or "people keep asking for a link to buy".
---

# Sales Page — order is the offer

Most first sales pages fail on order, not on words. They open with the product, hit you with a price before you want anything, and bury the proof at the bottom. This builds the page in the sequence that actually works: make them feel the problem, show them the after, then say what it is, what's inside, who else got it, and only then what it costs.

## Personalization
This skill works in *your* brand voice. Before running, load the brand profile at `~/.claude/brand-profile.md`.
- If it doesn't exist, run the **personalize** skill first (or just tell me your name, niche, offer, and audience — I'll create it).
- If a field this skill needs is blank, I'll ask one or two quick questions and save the answers back to the profile so you only answer once.
- Never invent facts or results about the user — use only what's in the profile, or ask.

## Steps

### 1. Check the offer is solid before you build a page for it
A good page cannot save a fuzzy offer. Two quick checks:

- **Do they have a price?** If no, stop and hand off to **pricing-calculator**, then come back. Building a sales page around "I'll figure out the number later" wastes the session.
- **Can they say in one sentence who it's for and what changes?** If that sentence comes out mushy — "it's kind of a coaching thing for anyone who wants to grow" — stop and hand off to **offer-builder**. Come back with a real offer.

If both are fine, keep going.

### 2. Gather the raw material
Ask for these. Keep the questions short and grouped.

- **The problem they feel.** Not the problem you diagnose — the one they'd complain about to a friend at 11pm. Their words.
- **The after-state.** What's true 90 days after this works. Specific and observable, not "more confident."
- **What it is.** The plain noun. A 6-week program. A 40-page template pack. A one-hour call plus a written plan.
- **What's included.** Every component, as a list. Sessions, files, access, support, timeframes.
- **Proof.** Real testimonials, real results, real credentials, real screenshots. Whatever they actually have. If they have nothing, say so — you'll use a different kind of proof in step 3 instead of inventing one.
- **The price**, and whether there's a payment plan.
- **The guarantee**, or their honest refund policy. "No refunds, here's why" is allowed and beats a fake promise.
- **The top three objections.** Too expensive, no time, will this work for someone like me, is this person legit, I've bought things like this before and didn't finish.

### 3. Write the page in this exact order — never reorder it
Write all the copy before touching the build. In their voice. Short sentences, concrete, no hype.

1. **The problem they feel.** Open here. Two or three lines that make them think "that's me." If they don't feel seen in the first five seconds, nothing after matters.
2. **The after-state.** Paint what changes, specifically. This is what they're buying — not your product.
3. **What it is.** One clear line naming the thing. Now that they want the outcome, tell them the vehicle.
4. **What's included.** A scannable list. Each item says what it does for them, not just what it is: "Six 45-minute calls — so you're never stuck for more than a week."
5. **Proof.** Testimonials with real names if they have them. If they don't have testimonials, use proof of the work instead: their own before-and-after, the process shown honestly, how long they've done this, a sample of the actual material. Never write a fake quote or invent a number.
6. **The price — said once, plainly.** One number, one payment-plan line if there is one, no anchoring theater, no fake discounts. Say it clean and move on. It appears exactly once on the page.
7. **The guarantee.** Removes the risk right after the number, where the flinch happens.
8. **FAQ killing the top three objections.** One question each, answered straight and short. Answer the objection, don't dodge it.
9. **A last short line and the button.**

The rule to state out loud: **never put price before value.** If a price appears before they want the outcome, it's just a number and it's always too big.

### 4. One button, three times
One call to action, same words, same color, three places down the page:
- Right after the after-state, for the person already sold.
- Right after the proof.
- At the very end, after the FAQ.

Same label every time — the button is a promise, not a variety show. "Join for $297" or "Get the template pack." Not "Submit," not "Learn more."

Where does it go? Their existing checkout link (Stripe, Gumroad, Lemon Squeezy, PayPal), or a booking link, or an email link if they're selling by conversation. Ask which they have. If they have none, use a mailto link with a pre-filled subject so they can still sell today, and note in the file where the real checkout URL goes later.

### 5. Build the page
One self-contained `index.html`:
- No build tools, no external JavaScript libraries. Google Fonts only — one display font, one body font, matched to their brand.
- One accent color plus neutrals. The accent belongs to the button and nothing else. Never the purple-to-blue AI gradient.
- Animation with transforms and opacity only, restrained. No animated blur or noise, no auto-scrolling marquees. No countdown timers.
- Fully readable with JavaScript off. Mobile-first — most sales pages are read on a phone in bed.
- Long-page typography: generous line height, comfortable reading width (around 65 characters), clear section breaks so it's scannable at speed.
- Real copy from step 3, never lorem ipsum. Inline SVG icons. Photos only if supplied or from a free Unsplash URL they approved.

Save to `~/sites/<slug>/index.html`.

### 6. Preview, run the loop, then the read-aloud test
Open it:

```bash
open ~/sites/<slug>/index.html
```

Ask them to read it out loud, all the way through. Anything they stumble over, they rewrite. Anything that makes them cringe about themselves is usually hype and comes out.

Then run the loop in plain words, 5-10 rounds. Two checks to repeat every couple of rounds:
- Does the price appear exactly once, and after the value?
- Is there anything on this page except the one button?

Write `~/sites/<slug>/NOTES.md` with the offer, the price, the three objections, the checkout destination, and the next step.

## Output — save it
- `~/sites/<slug>/index.html` — the full sales page, one file.
- `~/sites/<slug>/NOTES.md` — the offer in one line, the price, the three objections handled, where the button points, and tomorrow's next step.

State both paths. Single next action: run **deploy-it**, then send the link to three people who already told them they were interested.

## Example (input → output)
**Input:** "I coach new freelance designers. It's 6 weeks, group calls, $497. I've had 4 people through it and two of them landed clients."

**Output (saved to `~/sites/designer-coaching/index.html`, in order):**

- **Problem:** "You're good at the work. You just have no idea how to get someone to pay you for it — so you keep redoing your portfolio instead of sending the email."
- **After:** "Six weeks from now you've sent 30 real pitches, had at least three conversations, and you know exactly what to say when someone asks your rate."
- **What it is:** "A 6-week group program for designers getting their first paid clients."
- **Included:** "Six 90-min group calls — so you're never stuck for more than a week." Plus the pitch template, the rate script, a private thread for feedback.
- **Proof:** two named testimonials from the two who landed clients, stated as two of four — honest, not inflated.
- **Price:** "$497, or two payments of $260." Said once.
- **Guarantee:** "Come to the first two calls. If it's not for you, email me and I'll refund you in full."
- **FAQ:** "I have a full-time job — can I do this?" / "What if I have zero portfolio?" / "Why should I trust you?"
- Button **"Join for $497"** three times, pointing at their Stripe link.

## Notes / edge cases
- The failure this prevents: writing the page in the order the seller thinks (here's my thing, here's the price, please buy) instead of the order the buyer feels (this is my problem, that's the life I want, oh, that's what it costs).
- If they have zero proof, don't fake it. Show the work itself, be honest that they're early, and consider a lower founding price — that honesty converts better than an invented quote.
- If they want a countdown timer or fake scarcity, say no. If the deadline is real, state it as a plain sentence.
- If the page gets long and they panic, that's normal — long is fine when every section does a job. Cut sections that don't, not sentences that do.
- Hand off: **pricing-calculator** if there's no number. **offer-builder** if the offer itself is thin. **objection-handler** if the FAQ answers keep coming out defensive. **deploy-it** to publish.
