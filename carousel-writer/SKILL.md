---
name: carousel-writer
description: Get the exact words for every slide of a carousel post, plus a short note on what goes on each slide visually, so you can build it in Canva or have Claude build it as a web page. Slide 1 works as a standalone hook, one idea per slide, 7 to 10 slides, last slide is the ask. Use when the user says "write a carousel", "carousel post about", "turn this into slides", "swipe post", "I need the text for my carousel", "make this a 10 slide post", "what do I put on each slide", or "/carousel-writer".
---

# Carousel Writer — the words for every slide, in order

Carousels get saved and shared more than any other post, and people ruin them by putting a paragraph on slide one. This skill writes the text slide by slide, with the fewest possible words on each, and treats slide 1 as its own job: most people will only ever see that slide. It writes the words. It does not make the images.

## Personalization
This skill works in *your* brand voice. Before running, load the brand profile at `~/.claude/brand-profile.md`.
- If it doesn't exist, run the **personalize** skill first (or just tell me your name, niche, offer, and audience — I'll create it).
- If a field this skill needs is blank, I'll ask one or two quick questions and save the answers back to the profile so you only answer once.
- Never invent facts or results about the user — use only what's in the profile, or ask.

## Steps

### 1. Lock the one idea and the promise
Ask two things:
- "What's the one idea? Say it in a sentence."
- "What should someone be able to DO after swiping through this?"

If the answer to the second is "know more about me", stop. That's not a carousel, that's a bio. Push until the answer is a thing they can do or use.

Then decide the carousel type, and say which one you picked:
- **The list** — 5 to 7 things, one per slide. Easiest to save, easiest to make.
- **The walkthrough** — the steps of something they did, in order. Best when they built something.
- **The mistake** — what most people do wrong, why it fails, what to do instead.
- **The before/after** — the old way vs the new way, side by side across slides.

### 2. Write slide 1 like it's the only slide
Slide 1 is the whole post. Nothing else gets seen if it fails.

Rules:
- **Under 10 words.** Ideally under 7. If it needs a second sentence, it's not sharp enough.
- It must make a promise or a claim, not describe a topic. "5 free tools I use every day" beats "Thoughts on my toolstack."
- No name, no logo, no "swipe →" on slide 1. Give the words the whole frame.
- Big enough to read as a thumbnail with the phone at arm's length.

Write three versions of slide 1. Pick the strongest, say why in one line, keep the other two in the file.

### 3. Write the middle slides
One idea per slide. This is the rule that everything else depends on.

For each slide write:
- **Headline:** 3 to 8 words. This is what they read.
- **Support line (optional):** one short sentence, only if the headline genuinely can't stand alone. Most slides don't need it. Delete it if you're unsure.
- **Visual note:** one line telling them what goes on the slide — a screenshot of the thing, a big number, a two-column split, an arrow, or just the words on a plain background. Words on a plain background is a legitimate answer and often the best one.

Hard limits:
- Max 20 words of text on any single slide, including the support line.
- Never two ideas on one slide. If there's an "and", split it into two slides.
- Slide 2 should deliver the first piece of value immediately. No "here's what we'll cover" slide — that's a slide people swipe away on.
- Keep a thread pulling forward. Each slide should leave the next one worth swiping to.

Total: 7 to 10 slides including slide 1 and the CTA slide. Under 7 feels thin. Over 10 loses people.

### 4. Put something concrete in the middle
Somewhere between slides 3 and 6, one slide should carry proof: a real number, a screenshot of the thing they built, a real before/after, or a specific moment. This is the slide that makes the whole carousel believable.

Never invent the number. If there isn't one, use a screenshot or a concrete description instead.

### 5. Write the last slide — the CTA
The last slide does one job. One ask, never two.

Pick the right one:
- **Comment keyword** — best when there's a link, a template, or a file to send. "Comment TOOLS and I'll send you the list." One word, all caps.
- **Follow** — best when there's nothing to send yet. Say what they'll get if they do, specifically. "I post one build a week — follow if you're making something."
- **Save** — best on a list or reference carousel. "Save this for the next time you're stuck."

Write it in plain words. No "link in bio!!" energy, no exclamation marks.

### 6. Write the build instruction
Because this skill only writes words, end by giving them a ready-to-use instruction for actually making it. Include both options in the output file:

**Canva route:** one line per slide they can copy into text boxes, plus a note: pick one bold display font for headlines and one plain font for support lines, one accent color plus neutrals, and keep every slide's layout identical except the text.

**Claude route:** a copy-ready prompt they can paste into a new Claude Code session, written for them, along these lines:

> Build me a single self-contained `index.html` carousel with 9 slides, 1080x1350 each, that I can screenshot one at a time. No build tools and no JavaScript libraries. Use Google Fonts only — one bold display font for headlines, one plain font for body. One accent color plus neutrals, no purple-to-blue gradient. Every slide has the same layout: headline large and centered, optional support line beneath, lots of empty space. Here is the exact text for each slide: [paste slide text]. Add left/right arrow keys to move between slides. Make it readable with JavaScript turned off.

### 7. Final pass
- Read only the headlines, in order, top to bottom. Do they tell the whole story on their own? If not, the headlines are too vague.
- Cut the weakest slide. There's always one.
- Any slide over 20 words gets cut down or split.
- Banned words: unlock, leverage, elevate, game-changer, seamless, journey, empower.

## Output — save it
Write the result to `~/carousels/YYYY-MM-DD-<short-slug>.md` (create `~/carousels/` if needed).

The file contains: the one idea, the carousel type, every slide numbered with its headline / support line / visual note, the two runner-up slide 1 options, the caption to post with it (2 to 4 short lines, not a repeat of the slides), and both build routes including the copy-ready Claude prompt.

Tell the user the path, then the one next action: build slide 1 first and look at it on your phone before you build the rest.

## Example (input → output)
**Input:** "I want a carousel about the mistakes I made building my first website with AI. There were like 5 big ones."

**Output (saved to `~/carousels/2026-07-30-first-site-mistakes.md`):** Type: the mistake. 8 slides.

- **1.** `5 mistakes I made building my first site` — words only, plain background, huge type.
- **2.** `I asked for "a nice homepage"` / *Support:* "I got exactly what that means: nothing." — words only.
- **3.** `Vague in, vague out` / *Support:* "Say who visits, what you want them to click, and how it should feel." — words only.
- **4.** `I tried to fix the code myself` / *Support:* "I don't read code. I broke it worse." — screenshot of the broken page.
- **5.** `It took 9 rounds. That's normal.` — big number 9 filling the slide.
- **6.** `I waited until it was pretty` / *Support:* "Ugly and live beats perfect and on my laptop." — before/after split.
- **7.** `I didn't tell anyone I made it` — words only.
- **8.** `Comment SITE and I'll send you the prompts I used.` — words only, accent color.

## Notes / edge cases
- This skill writes text and describes slides. It does not generate images. Say that plainly if they expected pictures.
- The failure mode this prevents: a wall of text on slide 1 that nobody reads, followed by 9 slides nobody sees.
- If the idea can't survive being cut to 8 words per slide, it's not a carousel idea. Hand it to **thread-writer** instead — some ideas need sentences.
- If they have 15 points, they have two carousels. Make them pick the stronger 7 and save the rest.
- If every headline comes out sounding like everyone else's, the problem is the angle. Hand off to **positioning-filter**.
- Never fabricate a proof slide. A screenshot of a half-finished thing is worth more than a made-up number.
