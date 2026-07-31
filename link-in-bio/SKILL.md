---
name: link-in-bio
description: Build your own branded link-in-bio page in an evening — your photo, your name, your one-line pitch, and 4-6 buttons in the order that actually makes you money. Looks like you instead of like everyone else's Linktree, and it's built phone-first because that's where it gets opened. Use when the user says "/link-in-bio", "build me a link in bio", "I need a Linktree", "replace my Linktree", "a page for my Instagram bio", "one link with all my links", "link tree page", "bio link", "somewhere to put all my links", or "what do I put in my Instagram bio link".
---

# Link in Bio — your own page, not a rented one

Your Linktree looks like everyone else's Linktree, and the most valuable link on it is usually buried at the bottom. This builds your own page instead: your face, your words, your colors, and your links in a deliberate order. It's one file, it's yours, and nobody puts their logo at the bottom of it.

## Personalization
This skill works in *your* brand voice. Before running, load the brand profile at `~/.claude/brand-profile.md`.
- If it doesn't exist, run the **personalize** skill first (or just tell me your name, niche, offer, and audience — I'll create it).
- If a field this skill needs is blank, I'll ask one or two quick questions and save the answers back to the profile so you only answer once.
- Never invent facts or results about the user — use only what's in the profile, or ask.

## Steps

### 1. Gather the four pieces
Pull what you can from the profile, ask for the rest. Keep it to one short round of questions.

- **Photo.** A real photo of their face, or their logo if they're faceless. Ask for a file path on their computer, or tell them to save one to `~/sites/<slug>/photo.jpg` and say when it's there. If they have nothing right now, build with initials in a circle and note it as a fix for later.
- **Name.** How they want to be known. Not their legal name unless that's the brand.
- **One-line pitch.** What they do and who for, in under 12 words. Not a job title. "I help nurses start freelance writing" beats "Content Strategist & Consultant." Write three options and let them pick one.
- **The links.** Ask them to dump every link they'd want on there, unfiltered. Expect 8-12. You're going to cut it.

### 2. Order the links — this is the actual skill
Say this plainly: **the order is the whole thing.** People scan the first two buttons, tap one, and leave. Anything below button four is nearly invisible on a phone. So:

Run the sort in front of them:
1. **The money link goes first.** Whatever leads to income — the booking page, the product, the paid community, the service inquiry form. Not the free stuff. Not the YouTube channel. The money link. Beginners bury this every single time out of politeness. Name that habit out loud.
2. **The lead capture goes second.** Free guide, newsletter, waitlist. This is how someone who isn't ready to buy stays reachable.
3. **The best proof goes third.** One thing that shows they're real — a case study, a portfolio, the single best video.
4. **Everything else, ranked by how much it helps them.** Social profiles go last, if at all — the person is already on social; sending them back is a loop.

Then cut to **4-6 buttons total.** Not more. Ask: "If you could only keep four, which four?" Delete the rest without ceremony. A page with 11 links is a page where nothing gets clicked.

Rewrite each button label as a plain action or a plain thing, not a brand name. "Book a 20-min call" beats "Consulting." "Get the free client checklist" beats "Free Resources."

### 3. Build the page — phone first, always
Say why: 95 of every 100 people who open this are on a phone, coming from an app, with one thumb. So it's designed for a phone and merely doesn't break on a laptop.

Write one self-contained `index.html`:
- Single column, centered, max width around 480px so it stays readable on desktop instead of stretching.
- Buttons are full width, at least 52px tall, with real space between them. Big enough for a thumb, no zooming, nothing to mis-tap.
- Everything above the fold on a normal phone: photo, name, pitch, and the first two buttons visible without scrolling. Check this.
- No build tools, no external JavaScript libraries. Google Fonts only — one display font for the name, one body font. Match their brand.
- One accent color plus neutrals, used on the top button so the money link is visually loudest. Never the purple-to-blue AI gradient.
- Animation with transforms and opacity only — a small lift or scale on tap. No animated blur or noise, no auto-scrolling marquees.
- Works fully with JavaScript off. Every button is a plain link.
- Photo as a round image with a real `alt` description. Any icon as inline SVG. Real copy, never lorem ipsum.
- A one-line footer with their name and nothing else. No "made with" badge.

Save to `~/sites/<slug>/index.html`, with the photo alongside it in the same folder.

### 4. Preview at phone size
Open it:

```bash
open ~/sites/<slug>/index.html
```

Tell them to make the browser window narrow — about the width of a phone — because judging this at full desktop width will mislead them.

Ask: "Thumb-test it. Can you hit every button one-handed without thinking? Does the top button look like the most important one?"

Run the loop in plain words. Common real fixes: buttons too close together, name too small, photo too big pushing buttons below the fold, accent color too quiet to make the first button stand out.

### 5. Save the notes and hand off
Write `~/sites/<slug>/NOTES.md` listing the final link order and why, plus a line: "When something changes, re-run this and re-sort. The order should change as what you sell changes."

Close with: "Run **deploy-it** to get a real link, then paste it into your Instagram, TikTok, and email signature today."

## Output — save it
- `~/sites/<slug>/index.html` — the page, one file, phone-first.
- `~/sites/<slug>/photo.jpg` — their photo, if supplied.
- `~/sites/<slug>/NOTES.md` — final link order with the reason for each position.

State the paths. Single next action: run **deploy-it** and swap the link into their bio.

## Example (input → output)
**Input:** "I make videos about home coffee. I've got a Linktree with my YouTube, Instagram, TikTok, my Amazon list, my newsletter, a Discord, and a gear guide I sell for $19."

**Output (saved to `~/sites/coffee-page/index.html`):**

Photo. **Sam Ortiz.** "I help home coffee people stop wasting good beans."

1. **Get the $19 gear guide** (accent color, top of page — the money link, previously buried under three social icons)
2. **Free: my 1-page dial-in cheat sheet**
3. **Watch: the grinder video (2.1M views)** — only if that number is real and theirs
4. **Join the Discord**

Amazon list, Instagram, and TikTok cut. `NOTES.md`: "Socials removed — people arrive from social, sending them back is a loop. Revisit when the guide becomes a course."

## Notes / edge cases
- The failure this prevents: a wall of equal-looking links where the thing that pays gets tapped least. If they refuse to put the money link first, ask them to try it for two weeks and check the difference.
- If they have no money link yet, put the lead capture first and note in `NOTES.md` that position one is reserved for whatever they sell next. Hand off to **offer-builder**.
- If they have only two links, that's fine — build the two. Padding it with filler makes it worse.
- Never write follower counts, view counts, or client numbers you weren't given. Ask, or leave it out.
- Hand off: **deploy-it** to publish. **positioning-filter** if the one-line pitch keeps coming out generic. **landing-page** if one of the buttons deserves a real page of its own.
