---
name: quote-calculator
description: Build a small instant-quote widget for a service business — the buyer picks a few options and sees a price range right away, then leaves their contact details. Works for movers, cleaners, lawn care, painters, junk removal, detailers, handymen. One self-contained HTML file, no backend, nothing to pay for, and it's one of the easiest things a beginner can build for a local business and charge for. Use when the user says "build a quote calculator", "instant quote tool", "price estimator for my website", "let customers see a price", "pricing calculator", "estimate tool for my cleaning business", "something I can sell to local businesses", or types /quote-calculator.
---

# Quote Calculator — a price range in ten seconds, and a lead at the end

Service businesses lose most of their leads at the same place: someone wants to know roughly what it costs, the site says "call for a quote," and they call somebody else instead. A small calculator that gives an honest range fixes that. It's also one of the first things a beginner can build that a real local business will pay for, because it plugs a hole the owner already knows they have.

## Setup
None. This skill works out of the box.

## Steps

### 1. Get the business and the real pricing logic
Ask what the business does and who it's for. Then get the pricing, which is the whole job. Ask exactly this:

> "Walk me through how you actually price a job. What's the starting number, and what makes it go up? Give me one real recent job and what you charged for it."

Push until you have:
- **A base.** A minimum, a per-unit rate, or a starting price. There is always one, even if the owner has never said it out loud.
- **The 3-5 things that move the price.** Not ten. The things that actually swing the number. For a mover: size of home, distance, stairs or elevator, packing help. For a cleaner: bedrooms, bathrooms, one-time versus recurring, add-ons. For a painter: rooms, ceilings, prep condition. For junk removal: how much fits in the truck, stairs, heavy items.
- **How each one changes the number.** A multiplier ("2x for a two-story"), a flat add ("+$150 for packing"), or a per-unit rate ("+$35 per extra room").
- **The floor and the ceiling.** The smallest job they'd take and the biggest they'd quote without seeing it in person.

If they don't know their own numbers, don't invent any. Walk them through three real past jobs and reverse-engineer the pattern with them. Never make up prices for a real business.

### 2. Design the range, not the number
This is the rule that keeps them out of trouble: **always show a range, never a single hard number.**

A single number is a promise. When the crew shows up and the job is worse than described, the customer holds them to the number and someone eats the difference or the deal blows up. A range sets an expectation and keeps the conversation open.

- Build the range as roughly ±15-20% around the calculated midpoint, and round to clean numbers. `$340-$410`, not `$347.83-$412.19`.
- Widen the range when the inputs are vaguer. A "large home, lots of stuff" answer earns a wider spread than "3 bedrooms, 1,400 sq ft."
- Show the range big — it's the whole reason anyone touched the page.
- Put one honest line directly under it, in smaller type: "This is an estimate based on what you told us. Your final price is confirmed after a quick call or a photo." That sentence is the legal and human safety net.
- Add a plain-language breakdown under the range showing what drove it: "Base 3-bed clean $180 · Deep clean +$90 · 2 extra bathrooms +$50." People trust a number they can see the parts of.
- If an input puts the job outside what they'd quote sight-unseen, don't show a range at all. Show: "This one's big enough that a real quote beats a guess — leave your details and we'll call you today."

### 3. Capture the lead at the end, and only at the end
The range is what they came for. The contact form is what the business is paying for. Order matters.

- Show the range **first**, with no email required. Gating the number is why most of these tools fail — people leave rather than trade an email for a guess.
- Directly under the range, put the capture: name, phone or email, and one optional detail box. Three fields maximum.
- The button says what happens next. "Lock in this quote." "Send me the real number." Never "Submit."
- One line under the button setting expectations: "We'll call you within one business day. No spam."
- On submit, show the confirmation in place — no reload, no popup. Also save the full submission to `localStorage` (all their answers plus the calculated range) so the owner has a backup and can see it even before a form service is wired up.
- Where the lead actually goes, free options: a **Formspree** free endpoint pasted into the form's `action` (one signup, form stays on the page, roughly 50 a month free), a **Google Form** the page posts to (emails land in a sheet they already own), or a plain `mailto:` fallback that opens their email app. Build with the `mailto:` fallback and leave one clearly commented line at the top of the form where the real endpoint gets pasted. Tell them the exact line to swap.

### 4. Build the widget
One file. Bake in every one of these:

- One self-contained `index.html`. No build tools, no external JS libraries, no backend, no database. All the pricing math sits in plain JavaScript inside the file.
- Google Fonts is the only external resource. One display font for the price, one body font for everything else.
- Restrained palette: one accent plus neutrals. **Never** the generic purple-to-blue AI gradient. If `~/.claude/design.md` exists, read it and use that palette, font pairing, and spacing.
- Mobile-first, because most people fill these out on a phone standing in the room they want cleaned. Inputs at least 48px tall, big tap targets, one question per row on a narrow screen, no sideways scroll at 375px wide.
- Use the right input types so phones show the right keyboard: `type="tel"` for phone, `type="email"` for email, `type="number"` for counts.
- **Fully readable without JavaScript.** With scripts off, the page still shows what the business does, the list of options, the price range table or starting price in plain text, and a working contact form. The live calculation is the enhancement, not the page.
- The range updates the moment an option changes. No "Calculate" button — one less thing to tap.
- Animate with transforms and opacity only. The price number can fade and slide slightly when it changes. No animated blur, no noise filters, no marquees, nothing looping.
- Real copy throughout, written for this specific business. Never lorem ipsum.
- Icons inline SVG. No icon fonts, no image files.
- Include the viewport meta tag and a real `<title>`.
- Keep every price and multiplier in one clearly labeled block at the top of the script, with a comment above it: "All prices live here. Change these numbers to change every quote." The owner will want to raise prices next spring without calling anyone.
- Make it droppable: it works as a standalone page and also inside an `<iframe>` on an existing site. Say both options out loud when you hand it over.

### 5. Sanity-check it against real jobs
Before calling it done, run the three real jobs from step 1 through the calculator and compare. If the calculator says $290-$350 and they actually charged $520, the logic is wrong, not the customer. Fix the numbers and re-run.

Also check the edges: the smallest possible selection, the largest possible selection, and every option maxed out at once. If any of those produce a silly number, clamp it or route it to the "let's talk" message.

### 6. Tell them how to use it
Two paths, say both:
- **For their own business:** open the file, check it on a phone, then put it online free with Vercel's free tier or GitHub Pages, and link to it from their existing site as "Get an instant estimate."
- **For selling to a local business:** build one for a business in their town using that business's real public prices, send it to the owner as a working link, and say "I built this for you, want it on your site?" A working thing beats a pitch. This is a normal first paid job.

## Output — save it

Write the widget to `~/sites/<business-slug>-quote/index.html`.

Also write `~/sites/<business-slug>-quote/pricing-notes.md` with: the base price, every option and exactly how it moves the number, the range width, the floor and ceiling, the three real jobs you tested against and what the calculator returned for each, where the leads go plus the one line to swap, and a short "how to change your prices" note pointing at the labeled block in the file.

Tell them both paths, then:

> "Open `~/sites/<business-slug>-quote/index.html` and run one real job through it. If the range doesn't match what you'd actually charge, tell me what you'd have charged and I'll fix the numbers."

## Example (input → output)

**Input:** "My friend owns a junk removal company. He never posts prices and he says people call, ask what it costs, and hang up. He charges by how much fits in the truck."

**Output (saved to `~/sites/haulaway-quote/index.html`):**

- **Inputs:** how much stuff (quarter truck / half truck / three-quarter / full truck), stairs (none / one flight / two or more), heavy items (none / one / two or more), and same-day.
- **Logic:** base by truck fraction — $150 / $290 / $410 / $540. Stairs: +$40 per flight. Heavy items: +$75 each. Same-day: +20%.
- **Range:** midpoint ±15%, rounded to $10. A half truck, one flight of stairs, one heavy item shows **$345-$465**.
- **Under the range:** "Base half-truck load $290 · One flight of stairs +$40 · One heavy item +$75." Then: "This is an estimate based on what you told us. Your final price is confirmed when we see the load."
- **Over a full truck:** no range. Shows "That's a two-trip job — leave your number and we'll give you a real quote today."
- **Capture:** name, phone (`type="tel"`), optional "anything we should know." Button reads "Lock in this quote." Saved to `localStorage` and posted to a Formspree endpoint.
- **Look:** near-black text on bone, one orange accent on the price and the button only. The price fades and slides 4px when it changes. Works with JavaScript off — the plain price table shows instead.
- **Tested:** three of his past jobs came back at $310-$420 (he charged $380), $520-$700 (he charged $610), and $150-$210 (he charged $175). Close enough to ship.

## Notes / edge cases
- The beginner failure this prevents: building a big multi-page site for a local business when the one thing that makes the owner money is a price on the page.
- Never invent prices for a real business. If the owner can't say their numbers, reverse-engineer them from three real past invoices with the owner in the room.
- If they want a single exact number instead of a range, say no once and explain why: an exact number is a promise the crew has to keep sight-unseen. If they still insist, show a number and put "starting at" in front of it.
- More than five inputs and people quit halfway. If the owner wants nine questions, tell them the nine-question version gets fewer leads than the four-question version, and keep the extras for the follow-up call.
- Run **mobile-check** on it before it goes live — nearly everyone will use it on a phone. Use **make-it-designed** if it works but looks like a spreadsheet.
