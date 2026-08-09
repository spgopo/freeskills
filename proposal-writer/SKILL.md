---
name: proposal-writer
description: Turn messy notes from a call with a potential customer into a clean, ready-to-send proposal document. This is the written thing you send after you've set your price and had the conversation. Restates their problem in their own words, shows the outcome, lists exactly what they get, then puts the price where it already feels justified. Saved as a markdown file you can copy straight into an email. Use when the user says "write a proposal", "I had a call, now what do I send", "turn these notes into a proposal", "send them a quote", "they asked me to put it in writing", "how do I write this up", or types /proposal-writer.
---

# Proposal Writer: the document you send after the call

Someone talked to you. They're interested. Now they want it in writing, and you're staring at a blank page.

A proposal isn't a price list with your logo on it. It's a short document that shows the buyer you understood their problem, paints what changes when it's fixed, and then names the price after they already want the thing. Get that order right and the number stops being scary. This skill writes that document from whatever notes you've got, and saves it as a file you can paste into an email.

## Personalization
This skill works in *your* voice. Before running, load the brand profile at `~/.claude/brand-profile.md`.
- If it doesn't exist, run the **personalize** skill first, or just tell me your name, what you do, and who you do it for, and I'll create it.
- If a field this skill needs is blank, I'll ask one or two quick questions and save the answers back to the profile so you only answer once.
- Never invent facts or results about the user. Use only what's in the profile, or ask.

## What I need from you
Paste whatever you have. Rough call notes, a voice memo you typed up, a few bullet points, all of it works. I'll ask for anything missing.

1. **Who is this for?** Their name, their business, what they do.
2. **What did they say they need?** Their exact words if you wrote them down. Their own phrasing is the most valuable thing in your notes.
3. **What do they want to be true afterwards?** What "this worked" looks like for them.
4. **What are you going to do for them?** The actual work. This is the scope, meaning the list of what's in the job and what isn't.
5. **Your price.** One number is fine.
6. **Timeline.** When you can start and roughly how long it takes.
7. **Any guarantee you're comfortable with.** Optional. Skip it if nothing feels safe to promise.

## Steps

### 1. Read the notes and find the gaps
Pull the profile for their voice and any real proof they've already got. Then read the notes and check for the three load-bearing pieces: the buyer's problem, the scope, and the price.

If any of those three are missing, ask before writing. I won't guess a price and I won't invent scope. Everything else I can work around.

### 2. Restate the problem in their language
This is the section that decides everything. If the buyer doesn't feel understood here, no price will look reasonable.

Two or three sentences describing where they are now, using the words they used on the call. Concrete and specific to their business, not a generic version of their industry's problems.

If the user didn't capture the buyer's actual phrasing, write it plainly from the notes. Never fabricate a quote and put it in someone's mouth.

### 3. Write the outcome
What's different in their business once this is done. Concrete. Tie it back to something in the problem section so the two halves click together.

Not "improved efficiency." Something like "your front desk stops double-booking and the ten people a month who walk away because booking is a pain stay booked."

### 4. List the deliverables
A clean bulleted list of exactly what they get. Countable and specific.

Good: "3 landing page designs, plus 2 rounds of changes."
Bad: "design work."

Specific lists do two jobs at once. They make the price feel like it buys something real, and they protect the user later when the buyer asks for a fourth thing that was never in the list.

### 5. Build the price section
Put the price after the outcome, never before it. That ordering is called anchoring: whatever the reader sees first sets what everything after it feels like. Show the value first and the number lands against the value instead of against nothing.

Default to **two options** in a small table:

| Option | What's included | Price |
|---|---|---|
| Starter | the core deliverable on its own | lower price |
| **Complete (recommended)** | the core plus the parts that actually get the result | their price |

Put the user's number as **Complete** and mark it recommended. Build Starter by removing the pieces that aren't strictly required, and price it honestly for that smaller job.

Two options beats one, because a buyer choosing between two things is deciding *which*, not *whether*. Two also beats three for a first sale, because a third premium tier usually means promising ongoing work the user has never delivered before.

If they already ran **pricing-calculator** and have three tiers they can genuinely deliver, use all three.

Never change a number the user gave you. Suggest the structure, let them set the price.

### 6. Add the guarantee, only if they have one
A guarantee, sometimes called risk reversal, is you taking on some of the risk so the buyer doesn't carry all of it. "If it's not live by the delivery date, you don't pay the final half."

If the user doesn't have one they're comfortable with, cut the section. A guarantee they can't honor is worse than no guarantee.

### 7. End with one next step
One action, written as a sentence the buyer can do in ten seconds. "Reply 'yes' and I'll send the invoice and a short kickoff form. We start Monday."

Never end with "let me know your thoughts." That's how a proposal sits unread for three weeks.

### 8. Check the voice
Apply the profile's tone. Plain and confident, the way they'd talk to someone they respect. No "we are pleased to present." No hedging. The whole document should be readable in under two minutes.

## Output: save it
Write the proposal to `~/proposals/proposal-<client-slug>-<YYYY-MM-DD>.md`, creating the `~/proposals/` folder if it isn't there.

The file contains, in this order: title and date, the problem, the outcome, what they get, timeline, price table, guarantee if there is one, and the next step.

Tell the user the path. Then offer one thing: a short email or DM to send along with it, three or four lines, so the proposal doesn't arrive naked.

## Example (input → output)
**Input:** "Talked to Maria, runs a Pilates studio, 3 locations. Booking is paper and texts. She double-books constantly, figures she loses about 10 clients a month because booking is annoying. Wants online booking her front desk can run without training. I'd build the booking site and automatic reminders. Thinking $3,500. Can start next week, about 3 weeks of work."

**Output (excerpt, saved to `~/proposals/proposal-maria-pilates-2026-08-08.md`):**

> **Proposal for Maria, [Studio Name]. August 8, 2026**
>
> **Where you are now**
> Three locations, all booked by paper and text message. You're double-booking, your front desk is buried, and roughly ten clients a month walk away because booking is more effort than it's worth. Those are people who already chose you and you lost them at the door.
>
> **Where this gets you**
> One booking page across all three studios that your front desk can run on day one, automatic reminders so people show up, and no more double-bookings. The ten clients a month stay booked.
>
> **What you get**
> - Branded online booking site covering all 3 locations
> - Automatic text and email reminders
> - A simple front-desk view, no training needed
> - 2 rounds of changes and a 30 minute walkthrough call
>
> **Timeline:** start Monday, live in 3 weeks.
>
> **Price**
>
> | Option | What's included | Price |
> |---|---|---|
> | Starter | Booking site only | $2,200 |
> | **Complete (recommended)** | Booking site, reminders, front-desk view, walkthrough | **$3,500** |
>
> **My guarantee:** if booking isn't live and working across all three locations by the delivery date, you don't pay the second half.
>
> **Next step:** reply "let's go" and I'll send the invoice and a short kickoff form. We start Monday.

## Notes / edge cases
- The price is always the user's call. Suggest the structure, never move the number.
- If the notes are thin, ask three questions and stop. Don't write a proposal built on guesses, because the buyer will spot it in the problem section.
- If they haven't picked a number yet, send them to **pricing-calculator** first, then come back here.
- If the buyer hasn't actually agreed to receive a proposal, they don't need one yet. That's a conversation, and **first-customer-closer** handles it.
- Long doesn't mean serious. A one-page proposal that lands the problem beats six pages of process diagrams every time.
- Send it the same day if you can. Interest fades fast, and a proposal that arrives four days later has to rebuild the whole conversation.
