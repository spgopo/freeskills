---
name: testimonial-ask
description: Get the exact message to send asking for a testimonial, the three questions that produce a quote worth using, and a draft-it-for-them version that gets the highest reply rate. Also covers turning a rambling reply into a clean quote and asking permission to use it. Use when the user says "ask for a testimonial", "how do I get a review", "my client said they loved it, now what", "get a quote from a client", "I need social proof", "how do I ask for feedback without being awkward", "write a testimonial request", or "/testimonial-ask".
---

# Testimonial Ask — ask properly and get a quote you can actually use

Two things go wrong. Most people never ask, because it feels needy. The ones who do ask so vaguely they get "great to work with!" — which is warm, useless, and sells nothing. This skill writes the ask, times it, gives you three questions that produce a real quote, and shows you the version where you write it for them and let them edit.

## Personalization
This skill works in *your* brand voice. Before running, load the brand profile at `~/.claude/brand-profile.md`.
- If it doesn't exist, run the **personalize** skill first (or just tell me your name, niche, offer, and audience — I'll create it).
- If a field this skill needs is blank, I'll ask one or two quick questions and save the answers back to the profile so you only answer once.
- Never invent facts or results about the user — use only what's in the profile, or ask.

## Steps

### 1. Pick the moment
Timing matters more than wording. Ask at the peak, which is one of these:
- Right after they say something nice, unprompted. This is the best moment there is and almost everyone lets it pass. If they just sent "this is amazing", reply within the hour.
- The day the thing goes live, or the day they first use it.
- Two to four weeks after delivery, when they've seen a result. Slightly harder to trigger, but produces the best quotes because there's an outcome to point at.

Bad moments: during a problem, right after an invoice, or three months later when the feeling has faded.

Ask the user: "When did they last say something good about it, and how long ago was delivery?" Pick the moment from their answer and say which one you're using.

### 2. Write the ask
Rules for the message:
- Short. Under 80 words. A long ask feels like homework and gets postponed forever.
- Say exactly what you want and how long it'll take. "Three quick questions, two minutes."
- Give them an easy out. Removing pressure raises the reply rate, it doesn't lower it.
- Send it where you already talk to them — the same DM, text, or email thread. Never a form link. Forms kill reply rates.
- No flattery run-up. Get to it.

Standard version:

> Hey [name] — glad the [thing] is working out. Would you mind if I asked you three quick questions about it? Takes about two minutes and it really helps me when someone else is deciding whether to work with me.
>
> 1. What was the situation before we started?
> 2. What's specifically different now?
> 3. If someone was on the fence about doing this, what would you tell them?
>
> No rush, and totally fine if you'd rather not.

Adapt the wording to the user's voice and their actual relationship with this person. If they're friends, make it shorter and looser.

### 3. Understand why those three questions
Explain this to the user so they can improvise later. Each question produces a different piece, and together they make a complete quote:

1. **"What was the situation before?"** — produces the before-state. Without this, a testimonial is just praise. With it, a reader recognises themselves and keeps reading. This is the highest-value question of the three.
2. **"What's specifically different now?"** — produces the result. The word "specifically" is doing real work; drop it and you get "everything's better."
3. **"What would you tell someone on the fence?"** — produces objection-handling in the client's own words. This is the line that closes people, because it comes from someone who was in the same position.

Never ask "how did I do?" or "any feedback?" Those questions produce compliments, and compliments don't sell.

### 4. Shape a rambling reply into a clean quote
Most replies come back long, messy, and out of order. That's a good problem. Here's the rule: **you may cut, reorder, and tidy. You may not add.**

Allowed:
- Cut the filler, the greetings, the tangents.
- Reorder so before → change → recommendation.
- Fix obvious typos and turn spoken fragments into sentences.
- Trim to two or three sentences. Long testimonials don't get read.

Not allowed:
- Adding a number they didn't say.
- Making a claim stronger than what they wrote. "Saved me time" does not become "saved me 10 hours a week."
- Adding words they'd never use. If they don't talk like a brochure, the quote must not read like one.

Produce two lengths from the same reply: a **short pull-quote** (one or two sentences, for a website or a post) and the **full version** (three to five sentences, for a case study page).

Then send it back to them for approval — which is also how you get permission. See the next step.

### 5. Ask permission the easy way
Never publish a quote, a name, a company, or a photo without a clear yes. Combine the edit and the permission into one message:

> This is great, thank you. I tightened it a bit — here's what I'd use. Change anything that doesn't sound like you:
>
> "[the cleaned quote]"
>
> Okay if I use it with your first name and company? Happy to use just a first name, or keep it anonymous, whichever you prefer.

Offering the anonymous option makes people more likely to say yes to their full name, not less. If they don't reply, do not publish. Silence is not a yes.

### 6. The "make it easy" version — highest reply rate
Use this when the client is busy, slow to respond, or has already said something good you can build from. You write the quote, they edit it. Reply rates on this are far higher than the three-question version, because you've turned a writing task into a yes-or-no.

> Hey [name] — I'm putting together a couple of examples of my work and I'd love to include yours. To save you writing anything, I took a stab at it based on what you said:
>
> "[draft quote]"
>
> Feel free to change any of it, or rewrite it completely if it's off. And if you'd rather I didn't use it at all, that's completely fine.

Rules for the draft quote you write for them:
- Build it only from things they actually said or things you both know happened. This is the whole ethical line, and it's what makes this version legitimate rather than fabrication.
- Write it in their register, not yours. If they text in lowercase fragments, don't hand them a polished paragraph.
- Understate rather than overstate. A quote that's slightly modest gets approved instantly. One that's too strong makes them uncomfortable and they go quiet.
- Keep it to two or three sentences.
- If they change it, use their version, always.

### 7. Write the follow-up
One follow-up only, about a week later, one line:

> No worries if you're swamped — just bumping this in case it got buried.

If there's no answer after that, drop it. Never a third message.

## Output — save it
Write everything to `~/testimonials/<client-slug>.md` (create `~/testimonials/` if needed).

The file contains: the moment chosen, the ask message ready to send, the three questions, the "make it easy" draft version if relevant, the one-line follow-up, and a permission status line (`asked / approved / anonymous only / not yet`). When the reply comes in, the cleaned short quote and full quote go in the same file.

Tell the user the path, then the one next action: send the ask today, in the thread you already have with them.

## Example (input → output)
**Input:** "A guy I built a website for messaged me last week saying 'mate this is unreal, two people booked already'. I want a testimonial but I feel weird asking."

**Output (saved to `~/testimonials/dave-plumbing.md`):**

Moment: right after unprompted praise — send today, it's already a week old.

**Ask (make-it-easy version, because he's already given you the material):**
> Hey Dave — really glad it's pulling bookings already. I'm putting together a couple of examples of my work and I'd love to include yours. To save you writing anything, I had a go based on what you said:
>
> "Before this I had nothing online, people just had to know my number. Two people booked through the site in the first week. It was up in a few days and I didn't have to do anything."
>
> Change anything that doesn't sound like you, or tell me to bin it — no problem either way.

**Permission status:** not yet asked. Do not publish until he replies.

**Follow-up if quiet in a week:** "No worries if you're swamped — just bumping this in case it got buried."

## Notes / edge cases
- The failure mode this prevents: getting "great to work with!" and having nothing to show a prospect. Vague asks get vague answers, every time.
- If they're too nervous to ask, point out that the message has an easy out built into it. Nobody has ever damaged a relationship by asking once, politely, and letting it go.
- If the client is unhappy, do not ask. Fix the thing first. A testimonial ask during a problem makes the problem worse.
- If they have no clients yet, a testimonial from someone they helped for free is completely valid. Same message, same questions.
- Once the quote is approved, run **case-study** on the same project and put the quote inside it. Quote plus story beats either one alone.
- Never write a quote from scratch for someone who hasn't said anything positive. That's not a testimonial, and it will eventually cost more than it earns.
