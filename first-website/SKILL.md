---
name: first-website
description: Build your first real website by describing what you want in plain English — no code, no setup, one file you can open and see. Walks you through the Build Loop (describe, preview, react, repeat) for 5-10 rounds until the page looks right, then hands it off to be put online. Use when the user says "build me a website", "I want to make a website", "/first-website", "make me a site", "I need a page for my thing", "can you build a website for me", "I've never built a website", "I don't know how to code but I want a site", "make a homepage", or "build my first website".
---

# First Website — describe it, see it, fix it, ship it

You have never built a website, and you are not going to start by learning code. You are going to describe what you want, look at it, say what's wrong in normal words, and repeat until it's right. That back-and-forth is not you failing. That IS the job. At the end you have one real file on your computer that opens in a browser and looks like something you'd show a person.

## Setup
None. This skill works out of the box.

## Steps

### 1. Set the frame before you build anything
Tell the user, in two or three short sentences:
- They will not write or read any code. They describe outcomes; you build.
- You will build a first version fast, on purpose, so there's something to react to. It will not be right the first time. Good.
- They can't break anything. If a change makes it worse, they type `/rewind` (or hit Esc twice on an empty input box) and it goes back.

Then say: "Tell me about the site you want. Just talk — I'll ask what I need."

### 2. Get from vague to surgical
This is the whole skill. A vague brief gets a generic page. Take whatever they said and pull it into four specifics. Ask only for what's missing, and ask in plain words — never more than three questions at once.

- **The visitor.** Who lands here? Not "everyone." Someone specific: a bride looking for a photographer, a hiring manager checking if you're real, a friend of a friend who heard you fix bikes.
- **The one action.** What is the single thing you want them to do? Book a call. Email you. Read your work. Buy. Pick one. If they name two, make them rank and take the top one.
- **The feeling.** Three words for how it should feel. Calm and expensive. Loud and fun. Quiet and serious. This is what turns a template into their page.
- **The constraints.** What must be on it (name, photo, prices, a specific quote)? What must NOT be on it (no stock photos of handshakes, no pop-ups, no fake testimonials)?

Show them the difference out loud once, using their own topic:

> **Vague:** "Make me a website for my dog walking business."
> **Surgical:** "A one-page site for a dog walking business in Oakland. The visitor is a working dog owner who feels guilty their dog is alone all day. The one action is to text me to book a walk. It should feel warm, local, and reliable — not corporate. Must include: my name Maya, the neighborhoods I cover, $25 per walk, my phone number. Must not include: stock photos, a contact form, anything about 'pet care solutions'."

Say: "The second one gets you a site. The first one gets you a template. Everything you'll ever build with me works like this."

### 3. Build version one
Write a single self-contained `index.html`. Bake these in every time:

- One file. Everything inline — no build tools, no external JavaScript libraries, nothing to install.
- Google Fonts is the only outside thing you're allowed to load. One display font for headings, one body font. Pick fonts that match their three feeling words.
- One accent color plus neutrals. Never the purple-to-blue gradient every AI page has. If their feeling words are warm, the accent is warm.
- Animation only with transform and opacity, and only a little. No animated blur, no moving noise, no auto-scrolling marquees.
- The page must read fine with JavaScript off. Build mobile-first — most people will open it on a phone.
- Real copy written for their actual visitor. Never lorem ipsum. Never invented facts, prices, reviews, or credentials — if you need a number you don't have, ask or leave a clearly marked blank.
- Icons as inline SVG. Photos only if they gave you one, or a free Unsplash URL they approve.

Structure it simply: a headline that says what this is and who it's for, a short paragraph, proof or detail, and the one action as a single obvious button. One button. Repeated at most twice down the page.

Save to `~/sites/<slug>/index.html` where `<slug>` is a short lowercase name from their project (`maya-dog-walking`). Create the folders.

### 4. Preview and hand them the react prompt
Open it so they can see it:

```bash
open ~/sites/<slug>/index.html
```

(On Windows in a terminal that supports it, tell them to double-click the file instead.)

Then ask exactly this: **"Look at it. What's the first thing that bugs you?"**

Not "what do you think." Not "any feedback." One specific irritation at a time is what produces a good page. If they say "I don't know, it's fine," push once: "What would stop you from sending this to someone? Name one thing."

### 5. Run the loop, 5-10 rounds
Each round: they say one plain-English thing, you change it, they look again. Never ask them to touch the file.

Teach them to describe the symptom, not the fix. "The headline is too small on my phone" is a great note. "Change the h1 to 3rem" is not their job.

Good notes to model for them if they're stuck:
- "Too much space at the top before I see anything."
- "The button doesn't look clickable."
- "This feels like a corporate brochure, I want it friendlier."
- "The words are hard to read on that background."

Every 2-3 rounds, say: "That's a good checkpoint — want me to commit this as a checkpoint?" and if yes, make a permanent save with Git so they can always come back to this exact version.

Stop the loop when they'd send it to a person. Not when it's perfect. Perfect isn't coming today.

### 6. Write the note file and hand off
Write `~/sites/<slug>/NOTES.md` with what the site is, who it's for, the one action, the feeling words, and a one-line "next time I'll..." so tomorrow's 90 minutes starts with a read instead of a stare.

Then close with the handoff, in these words:
"Right now this only exists on your computer. Run **deploy-it** and I'll get it on a real web address for free. Then send that link to one actual human today — not to show off, just to have shipped something. Ugly but live beats pretty but sitting in a folder."

## Output — save it
- `~/sites/<slug>/index.html` — the working site, one file, opens in any browser.
- `~/sites/<slug>/NOTES.md` — what it is, who it's for, the one action, the three feeling words, and tomorrow's one-line next step.

Tell the user both paths out loud. Single next action: run **deploy-it**.

## Example (input → output)
**Input:** "I want a website for my dog walking thing. I walk dogs in Oakland. I don't really know what should be on it."

**Output (after the surgical pass and 6 rounds, saved to `~/sites/maya-dog-walking/index.html`):**

A one-page site. Big warm headline: **"Your dog doesn't have to spend the whole day alone."** Under it: "Maya walks dogs in Rockridge, Temescal, and Piedmont Ave. 30 minutes, $25, photo sent every time." Three short blocks: *Same walker every time* / *A photo from every walk* / *Text me by 9am for a same-day spot*. One accent color (a soft rust orange), one display font, one body font. A single big button that says **Text Maya — (510) 555-0143** and nothing else competing with it.

`NOTES.md` ends with: "Next time: add the two photos of Rocco and Juno from my phone."

## Notes / edge cases
- The failure this prevents: a beginner asking for "a website," getting a generic template, feeling nothing, and quitting. The surgical pass in step 2 is not optional — do it even if they're impatient.
- If they give you only one line and won't answer questions, build something anyway and let them react to it. Reacting is easier than briefing, and one bad version beats an empty page.
- If they ask for a login, a database, payments, or a blog with many posts, say plainly that's a bigger build and today's job is one page that works. Note it in `NOTES.md` as a later step.
- Never invent prices, testimonials, client names, or results. If a section needs a number they don't have, leave a marked blank and tell them what to fill in.
- Hand off: **deploy-it** to put it online. **landing-page** if the real job is capturing emails, not introducing them. **link-in-bio** if they actually just needed a button list for social.
