---
name: repeatable-offer
description: Offer-builder makes an offer irresistible. This one makes your service repeatable, so you stop quoting from scratch every time someone asks what it costs. Finds the part of your work that's the same on every job, then wraps it in a fixed name, a fixed scope, a fixed price, a fixed timeline, and a delivery checklist you run the same way every order. Use when the user says "make this repeatable", "I keep doing this custom for everyone", "package what I do", "turn my service into a product", "I'm quoting every job from scratch", "productize my service", "I'm stuck trading time for money", or "/repeatable-offer".
---

# Repeatable Offer: sell the same thing twice

Custom work is exhausting because every sale starts at zero. You re-explain what you do, guess at a price, and then the job grows past what you agreed to. The fix is to find the part of the work that's the same on every job, put a box around it, and sell that box over and over. That's what "productizing" means: turning a service into something with edges, like a thing on a shelf.

The output is a one-page offer you can send to a buyer and also follow yourself while you deliver.

## Personalization
This skill works in *your* brand voice. Before running, load the brand profile at `~/.claude/brand-profile.md`.
- If it doesn't exist, run the **personalize** skill first. Or just tell me your name, niche, offer, and audience, and I'll create it.
- If a field this skill needs is blank, I'll ask one or two quick questions and save the answers back to the profile, so you only answer once.
- Never invent facts or results about the user. Use only what's in the profile, or ask.

## Steps

### 1. Find the repeatable core
Ask them to walk through the last 2 or 3 times they did this work, job by job. Then look for what was the same every time. That's the 80% that repeats no matter who the client is, and it's the actual product. The rest is noise that feels important because it was different.

Two questions do most of the work:
- "What do you do on every single one of these, no matter who it's for?"
- "What's the thing the client actually cares about at the end?"

Write the core as one sentence: "I take [input] and turn it into [outcome]." If they can't finish that sentence yet, keep asking about the last few jobs. Don't move on with a vague core, because everything after this is built on top of it.

### 2. Define one fixed deliverable
Now replace "it depends" with a concrete thing the buyer receives. Consulting is not a deliverable. A built website, a set of five posts, a working automation plus a video walkthrough: those are deliverables, because you can point at them.

- Write out exactly what they get, as a short bulleted list.
- Write what "done" looks like, so both sides know when it's finished.

That finish line matters more than it sounds. Most of the pain in custom work comes from nobody agreeing when the job ended.

### 3. Set a fixed timeline
A product has a delivery time. Give it one and say it plainly: "delivered in 7 days", "a 2 week sprint", "live within 48 hours".

Pick the realistic outer edge, not the best case. A timeline you beat makes you look good, and a timeline you miss costs you the referral. The timeline is also a selling point on its own, because most people who buy services have no idea when they'll get anything.

### 4. Draw the box around the scope
This is the hard step and the one people skip. Write down what is NOT included. Scope creep is when a job quietly grows past what was agreed, and it's the thing that turns a product back into custom work.

- Name the requests you'll say no to.
- Cap the variables with real numbers: "up to 5 pages", "one revision round", "one platform".
- Take the extras people keep asking for and turn them into named add-ons with their own price. A paid add-on is a yes. A free extra is a leak.

End with three plain lists: included, not included, add-ons with prices.

### 5. Name it and price it
Give it a name that says the outcome, not the process. "Inbox Rescue" beats "Automation Consulting Package." Keep it short enough to say out loud.

Then write the one-line promise: "You get [deliverable] in [timeline], done for you."

Then put a fixed number on it. Price on what the outcome is worth to the buyer, not on how many hours it takes you, because hours punish you for getting faster. If they're stuck on the number, hand off to **pricing-calculator**. If they want to stack this into a bigger, harder to refuse offer with a guarantee and bonuses, that's **offer-builder** after this.

### 6. Pick how it gets delivered
Fulfillment just means how the work actually gets done and handed over. Pick one:

- **Do it yourself.** They buy templates or a tool and run it themselves. Cheapest to deliver, scales the furthest.
- **Do it with you.** You have a set process and calls where you guide them. Repeatable, higher touch, higher price.
- **Done for you.** You run your fixed process on their behalf. Highest price, and you cap your slots so quality holds.

Then write the standard delivery steps, the same checklist run on every single order: intake, build, review, handoff. This checklist is the part that makes it repeatable in real life instead of on paper. It's also what you'd hand to the first person you hire.

## Output: save it
Write the one-page offer to `~/offers/<product-name>.md` (create `~/offers/` if needed, and turn the name into a filename, so "Inbox Rescue" becomes `inbox-rescue.md`).

The file contains: the repeatable core sentence, the deliverable spec, the timeline, the included and not included and add-on lists, the name plus one-line promise plus price, the fulfillment model, and the delivery checklist.

Tell them the path, then give one next action: send the one-line promise to one person who fits, and see what they ask about. The questions they ask are the parts of the box that aren't clear yet.

## Example (input → output)
**Input:** "I do freelance automation help. Every job is different, I quote it off the top of my head, and the work always grows."

**Output (saved to `~/offers/inbox-rescue.md`):**
- **Repeatable core:** I take a small business's messy lead intake and turn it into one automatic pipeline.
- **Deliverable:** a connected intake form, feeding a CRM (the tool that stores customer contacts), plus an automatic reply to every new lead, plus a short video walkthrough.
- **Done means:** a test lead comes in and gets a reply without anyone touching it.
- **Timeline:** live in 5 business days.
- **Included:** one intake source, one CRM, one auto-reply sequence.
- **Not included:** custom code, more than one brand, ongoing changes after handoff.
- **Add ons:** extra reply sequence $200. Second location $400.
- **Name, promise, price:** "Inbox Rescue. Your leads captured and answered automatically in 5 days, done for you. $1,200."
- **Fulfillment:** done for you, 4 slots a month.
- **Delivery checklist:** intake call, map their current flow, build it, test with sample leads, walkthrough and handoff.

## Notes / edge cases
- If nothing repeats across their last few jobs, they're not ready to productize this whole service yet. Pick the single request they get most often and box up that one first. One narrow product beats a flexible one that never gets sold twice.
- Resist making the product do everything. A boring, narrow, repeatable offer outsells a clever custom one, because a buyer can understand it in ten seconds.
- If they've only ever done this once, they're guessing at the core. Do the next job, take notes on what you actually did, then run this again with real material.
- The finished one-pager does double duty. It's the sales page you send to buyers, and it's the checklist you follow while delivering, so both sides of the job stay the same every time.
- Revisit it after five orders. By then you'll know which add-on people always buy, and that one usually belongs inside the box at a higher price.
