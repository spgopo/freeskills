---
name: first-product
description: Turn what you already know into one finished digital guide you can sell, in a single sitting. Interviews you about your angle and your lessons, writes the whole guide as a clean file you can turn into a PDF, then writes the storefront listing copy (title, pitch, price, three bullets) and the short checklist of things you still have to do by hand. Use when the user says "help me make a digital product", "turn my knowledge into an ebook", "build a guide I can sell", "make me something to put on Gumroad", "I want to sell a PDF", "what can I sell", or "/first-product".
---

# First Product: one guide, written and ready to sell tonight

Most people never sell anything because they're waiting to build the big thing. A first product doesn't need to be big. It needs to be one focused guide that teaches one person how to get one result, sold for a small price on a storefront (a simple page that takes payment and hands over your file, like Gumroad or Stan Store).

This skill writes that guide with you. Not an outline, not a plan. The actual 20 to 40 pages, plus the copy for the product page. You finish the sitting owning a real product.

## Personalization
This skill writes in *your* voice, about *your* expertise. Before running, load the brand profile at `~/.claude/brand-profile.md`.
- If it doesn't exist, run the **personalize** skill first (or just tell me your niche, your audience, and the result you help people get, and I'll create it).
- If a field this skill needs is blank, I'll ask one or two quick questions and save the answers back to the profile so you only answer once.
- Never invent numbers, results, or claims the user didn't give you.

## Steps

### 1. Get the three basics
Pull these from the profile first, and only ask for what's missing:
1. **What you know how to do.** The actual skill, not a job title.
2. **Who it's for.** One kind of person, named specifically.
3. **The result.** What changes for them after they follow your method.

If the opening message is thin ("help me build something to sell") and the profile doesn't cover it, ask for these three before anything else. Don't guess at someone's expertise. A wrong guess here makes the whole guide wrong.

### 2. The interview: four questions, no more
Ask only what's still missing. Never turn this into a ten-question intake. Speed is the point.

1. **Your angle.** What makes your version of this different? A specific moment, a result, a mistake you made. This becomes the hook, and it's the reason someone buys from you instead of googling the topic for free.
2. **Your lessons.** Three to five things you'd teach someone starting from zero. These become the chapters. If they can't name them, propose a set based on their niche and confirm before writing.
3. **A writing sample.** A post, an email, a video transcript, anything they've written. If they paste one, match it. If not, use the Tone in the brand profile, and always use their own words for their own niche.
4. **The price.** If they don't know, recommend one and give the reason in a line. Don't hand them a menu:
   - $9 to $27 for a focused guide on one topic
   - $27 to $47 if it comes with templates, worksheets, or swipe files
   - $47 to $97 if it replaces something they'd otherwise pay hundreds for

On length: most first products run 20 to 40 pages, around 4,000 to 8,000 words. Default to short unless they say otherwise. A guide that gets finished and read beats a long one that doesn't.

### 3. Confirm the chapter list
Turn the lessons into a chapter list and show it as a short numbered list. Intro, one chapter per lesson, closing chapter.

This is the one checkpoint. Get a yes here, because a wrong structure wastes the whole write. Keep it to the list. No pitch, no preamble.

### 4. Write the whole guide
Every chapter is built around ONE unlock: something the reader can do after reading it that they couldn't before. Not a pile of information.

Per chapter:
- Open with the real situation the reader is in, not a definition.
- Teach the one unlock plainly, with a real example. Use the user's own story where you have it, otherwise a plausible scenario in their niche framed as an example ("say you're trying to...").
- Give the exact action to take, not just the idea.
- Short paragraphs. White space does work.

Voice rules for every sentence:
- Fifth to eighth grade words. If a term is necessary, explain it in plain words the first time it shows up.
- One idea per sentence. Break anything running past about 20 words. Contractions on.
- No filler openers ("In today's world", "Let's dive in"). No hedging ("might", "could", "perhaps"). Say the thing.
- No saying the same point three ways to hit a page count. If it's said, move on.
- No clever lines that sound smart but don't tell the reader what to do.
- Never invent a stat, a client result, or a claim the user didn't give you.

Before a chapter is done, check it: could it be summarized as "here's some background on X"? Then it isn't done. Cut the background and get to the unlock.

### 5. Format it so it converts to PDF cleanly
Write the guide to a single Markdown file in this shape:

```markdown
# [Guide Title]
### [One line saying what changes for the reader]

*by [Author Name]*

---

## Introduction
[The angle and story. What they'll walk away able to do. Who this is for, in a sentence.]

---

## Chapter 1: [Lesson]
[Situation, then the unlock, then the exact action.]

---

## Chapter 2: [Lesson]

(repeat for each lesson, three to five total)

---

## Putting It Into Practice
[The single next action to take this week.]
```

Print-safety rules, because free Markdown-to-PDF converters break on the rest:
- H1 for the title, H3 for the subtitle, H2 for chapters. Nothing deeper.
- No tables. Use short prose or a plain bullet list to compare things.
- No code blocks. They render as ugly grey boxes in an ebook.
- Bullet lists one level deep only. Nested bullets collapse.
- Bold sparingly, for emphasis only. Never bold a whole sentence.
- A `---` between sections, which gives most converters a clean page break.
- No images, no HTML. Keep it plain so it pastes into Notion or Google Docs without breaking.

Don't try to generate a PDF. The deliverable is the clean file. Tell the user plainly: paste it into Notion, Google Docs, or a free Markdown-to-PDF tool and export. That PDF is what gets uploaded.

### 6. Write the storefront listing copy
This is the copy for the product page itself. Write it in this exact shape:

```
TITLE: [short, says the benefit, matches the guide title]

PITCH (3 to 5 sentences): who it's for, what changes for them, why this person
specifically can teach it (their real angle from step 2), and what makes it
different from the free stuff on the same topic.

PRICE: $[X], because [one line tied to what the result is worth].

WHAT YOU'LL BE ABLE TO DO:
- [concrete thing]
- [concrete thing]
- [concrete thing]
```

Keep the pitch grounded in the real result. Never inflate it with numbers the user didn't give you.

### 7. The honest checklist of what's left
This skill can't touch a storefront or a payment account, so always close by saying exactly what's left. Nothing here is automatable from a skill:

```
WHAT YOU DO BY HAND:
[ ] Make a storefront account (Gumroad, Stan Store, or Payhip, pick one)
[ ] Connect a payment account (usually Stripe) so you can get paid
[ ] Convert guide.md to PDF (paste into Notion or Docs, export as PDF)
[ ] Create a new product in your storefront and upload the PDF
[ ] Paste in the title, pitch, and bullets from listing.md
[ ] Set the price
[ ] Publish, and send the link to one real person today
```

## Output: save it
Create `~/guides/<guide-slug>/` and write two files:
- `guide.md`, the full guide, print-safe.
- `listing.md`, the listing copy from step 6 plus the checklist from step 7.

Tell the user both paths. Then one next action: convert `guide.md` to a PDF, because everything else waits on that file existing.

## Example (input → output)
**Input:** "I've been doing dog training for six years. Mostly reactive dogs. People come to me after they've tried three other trainers. The thing I always end up teaching is that they're rewarding the wrong moment."

**Output (chapter list, confirmed before writing):** Introduction, the client who'd fired three trainers before me. 1. Why your dog reacts before you even see the trigger. 2. The two second window that decides everything. 3. Rewarding calm instead of rewarding quiet. 4. Walking a reactive dog without dreading the walk. Then Putting It Into Practice.

**Output (excerpt from `~/guides/reactive-dog-reset/listing.md`):**
> TITLE: The Reactive Dog Reset
>
> PITCH: For owners whose dog lunges, barks, or freezes on every walk, and who've already tried the usual advice. This is the six year version of what I teach clients who come to me after other trainers. You'll learn to spot the moment before the reaction, and what to reward instead. It's specific to reactive dogs, not general obedience.
>
> PRICE: $27, because one in person session costs more than this and covers less.

## Notes / edge cases
- If they want a course, a series, or a whole book, say so plainly and point them back here. One guide, finished, beats a course nobody ever launches.
- If they can't name their lessons, that's normal. Propose three to five from what they told you in step 1 and let them correct you. People find it easier to edit than to invent.
- If they have no proof or results yet, don't fake any. The angle carries the guide. A specific method taught well is worth paying for without a testimonial attached.
- If the price question stalls them, pick the low end and move. They can raise it after the first ten sales.
- If they have a next offer to point readers at, ask before adding a mention at the end. Never bolt one on without asking.
- The chapter list is the only checkpoint. Once it's confirmed, write the whole thing in one go. Stopping to check every chapter is how a one sitting product turns into a three week project.
