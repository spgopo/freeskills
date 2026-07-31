---
name: rewrite-plain
description: Rewrites anything into plain, direct language a busy person understands on the first read. Kills jargon, hedging, passive voice, throat-clearing openers, and the corporate words that mean nothing — while keeping your meaning and every fact exactly as they were. Shows a short before/after so you start spotting the pattern yourself. Works on emails, posts, bios, sales pages, docs, anything. Use when the user says "make this simpler", "this sounds corporate", "rewrite this", "plain English", "clean this up", "make this clearer", "does this make sense", "too wordy", "dumb this down", "tighten this", or /rewrite-plain.
---

# Rewrite Plain — say it so it lands first time

Unclear writing isn't a vocabulary problem. It's usually someone hedging, or hiding, or warming up for three sentences before they say anything. This skill strips that out and leaves the meaning intact. It is a clarity pass, not a rewrite of your argument — same facts, same position, same claims, said so a busy person gets it on one read.

## Personalization
This skill works in *your* brand voice. Before running, load the brand profile at `~/.claude/brand-profile.md`.
- If it doesn't exist, run the **personalize** skill first (or just tell me your name, niche, offer, and audience — I'll create it).
- If a field this skill needs is blank, I'll ask one or two quick questions and save the answers back to the profile so you only answer once.
- Never invent facts or results about the user — use only what's in the profile, or ask.

## Steps

### 1. Get the text and one piece of context
Take the text (pasted, or a file path). Ask one question only: **"Who reads this, and what do you want them to do after?"** If they already said, skip it.

That answer sets how much you can cut. A sales page for strangers and a note to your accountant get different treatment.

### 2. Find the point
Read it and write down, for yourself, the single sentence that is the actual point. Then check where it sits in the original — usually paragraph two or three, buried behind the run-up.

If you can't find a point, stop and say so: "I can't tell what you're asking for here. What's the one thing you want them to know?" A clear rewrite of an unclear idea is still unclear.

### 3. Cut the seven things
Work through the text and remove:

1. **Throat-clearing openers.** "I hope this finds you well." "In today's world." "As you may know." "I wanted to reach out to." Delete and start at the real first sentence.
2. **Hedging.** "just", "kind of", "sort of", "I think maybe", "perhaps", "I could be wrong but", "does that make sense?". Say the thing. Keep a hedge only when the uncertainty is real and matters.
3. **Passive voice hiding the actor.** "Mistakes were made" becomes "I got the date wrong." Passive is fine when the actor genuinely doesn't matter; it's not fine when it's dodging.
4. **Corporate words that mean nothing.** leverage, utilize, synergy, holistic, robust, seamless, empower, unlock, elevate, streamline, best-in-class, value-add, solutions, going forward, circle back, touch base, deep dive, at the end of the day, moving the needle.
5. **Nominalizations** — verbs turned into nouns. "make a decision" is "decide". "provide assistance" is "help". "has a requirement for" is "needs".
6. **Long words doing a short word's job.** utilize/use, commence/start, terminate/end, prior to/before, in order to/to, additional/more, sufficient/enough, approximately/about, currently/now.
7. **Repeats.** The same point made twice in different clothes. Keep the better one.

### 4. Rebuild it
Now put it back together:

- **Point first.** The thing they need to know goes in the first two lines.
- **One idea per sentence.** Break any sentence over about 25 words at its natural joint.
- **Short paragraphs.** One to three lines. White space is readable.
- **Concrete over abstract.** "£1,800, five weeks late" beats "an outstanding balance." Names, numbers, dates, objects.
- **Verbs over nouns.** "We decided" beats "a decision was reached."
- **Keep their real words.** If they said something well in the original — a phrase that sounds like a person — keep it exactly. Don't smooth a good line into a bland one.
- **Read it aloud in your head.** If you'd run out of breath or stumble, cut it there.

Aim for 30–50% shorter. Say the final word count and the original.

### 5. Guard the meaning
Before showing it, check the rewrite against the original line by line:

- Every fact, number, date, name, and claim survives unchanged.
- No new claim, promise, or number appeared. Not one.
- The position didn't soften or harden. If they hedged deliberately about something genuinely uncertain, that hedge stays.
- Nothing legally or factually load-bearing got dropped as "wordy" — caveats in contracts and disclaimers are usually there for a reason.

If cutting a phrase would change the meaning, keep it and say why in one line.

### 6. Show the pattern
Under the rewrite, show **three to five before/after pairs** from their own text — one line each. Pick the ones that teach the most, and name the move in two or three words.

> **Before:** "We wanted to reach out in order to provide you with an update regarding the current status of the project."
> **After:** "Here's where the project is."
> *Cut: throat-clearing + nominalizations.*

This is the part that makes them better next time. Don't skip it, and don't do more than five — it stops teaching and starts nagging.

## Output — save it
Write to `~/rewrites/<short-slug>-<YYYY-MM-DD>.md` (create `~/rewrites/` if needed):

```
# Rewrite — <what it is>
## The rewrite
<clean, paste-ready, nothing else in this section>
## Word count
## What I changed and why
## Before / after — the patterns
## Original
```

Keep the original at the bottom so nothing is lost. Tell the user the path, and paste the clean rewrite straight into your reply so they can copy it without opening anything.

## Example (input → output)
**Input:** A bio for a website: "With over a decade of experience in the industry, I leverage a holistic, data-driven approach to empower businesses of all sizes to unlock their full potential through the utilization of best-in-class digital solutions tailored to their unique needs."

**Output (saved to `~/rewrites/bio-2026-07-30.md`):**

> **The rewrite:** "I've spent ten years helping small businesses fix their websites and get more customers from them. Mostly shops, trades, and one-person studios."
>
> **Word count:** 44 → 26.
>
> **Before / after:**
> - **Before:** "leverage a holistic, data-driven approach" → **After:** cut entirely. *It says nothing, and cutting it lost nothing.*
> - **Before:** "businesses of all sizes" → **After:** "small businesses. Mostly shops, trades, and one-person studios." *All sizes means nobody pictures themselves. Naming three types means three types recognise themselves.*
> - **Before:** "through the utilization of best-in-class digital solutions" → **After:** "fix their websites". *Say the actual job.*
> - **Before:** "over a decade of experience" → **After:** "ten years". *Same fact, one less mask.*

## Notes / edge cases
- The beginner failure mode this prevents: writing to sound professional and ending up sounding like nobody. Plain is not unprofessional. Plain is confident.
- This is a clarity pass. Never change their argument, soften a "no", strengthen a claim, or add a number they didn't give you. If you think the argument itself is wrong, say so separately — don't fix it silently in the rewrite.
- If the text is already clear, say so and make three small cuts rather than manufacturing a rewrite. Not everything needs surgery.
- Technical terms stay when the reader knows them. Plain means "no words that hide meaning", not "no specific words". Cutting the right term for a vague one makes it worse.
- Legal, medical, or contract wording: flag anything you'd cut rather than cutting it, and suggest a professional check.
- If they need the whole email written rather than tidied, use **email-writer**.
