---
name: design-taste
description: Turn "I don't have taste" into a written design system you own. You name or screenshot 1-3 sites you love, and this reverse-engineers the exact colors, font pairing, spacing rhythm, and rules underneath them, then saves a design file every future build reads so your stuff stops looking like a default template. Use when the user says "I don't have taste", "my site looks generic", "why does everything I build look the same", "make me a design system", "pick my colors and fonts", "my stuff looks like AI made it", "help me choose a font", "set my brand colors", or types /design-taste.
---

# Design Taste — steal like a designer, write it down

Nobody is born with taste. Taste is a set of decisions someone already made, written down so you stop re-deciding every time. This skill looks at 1-3 sites you already like, pulls out the actual decisions inside them (hex codes, font pairing, spacing steps, how much empty space, how big the headline is compared to the body), and writes them into one file. From then on, every build reads that file, and your pages start looking like they came from the same person — because they did.

## Setup
None — this skill CREATES the design file other skills read.

## Steps

### 1. Get 1-3 references and one sentence about the feeling
Ask exactly this, in one message:

> "Name or paste 1-3 sites you love the look of. Any sites — a brand you buy from, a landing page you bookmarked, a portfolio. If you have screenshots, drop them in. Then finish this sentence: 'I want people to feel ___ when they land on my page.'"

Rules:
- If they give a URL, fetch the page and read the real CSS values where you can. If you can't fetch it, say so plainly and work from what you know of the site plus their screenshot.
- If they give a screenshot, read the colors and type off the image.
- If they say "I don't know any," don't stall. Offer six named directions and let them pick one: **editorial print** (big serif headlines, cream paper, one ink color), **Swiss utility** (tight grid, one bold sans, lots of white), **warm minimal** (off-white, soft shadows, one muted accent), **dark technical** (near-black, mono type, one bright signal color), **retro poster** (thick display type, two flat colors, hard edges), **quiet luxury** (huge margins, small type, near-no color).
- Never accept more than 3 references. Four references is a mood board, not a system.

### 2. Reverse-engineer the decisions, not the vibe
For each reference, write down the concrete stuff. Say what you actually see:
- **Colors:** the page background, the main text color, the one accent, and any surface/card color. Give hex codes. Most good sites use 4-6 colors total, and the accent appears on less than 10% of the page.
- **Type:** the display face (headlines) and the body face. Name both. Note whether it's serif + sans, sans + sans, or sans + mono.
- **Size jump:** the ratio between the big headline and body text. Good sites are confident — a headline is often 3-5x the body size, not 1.5x.
- **Spacing:** how much air sits above and below sections. Note whether it's tight or generous.
- **Corners and edges:** sharp corners, small radius, or pill. Pick one, they never mix.
- **What it does NOT do.** This matters more than the rest. Note the absences: no gradients, no drop shadows, no icons, no stock photos of people in offices.

Then say one honest line about what the references have in common. If they have nothing in common, tell the user that and make them pick which one wins.

### 3. Build the system
Turn the observations into a set of decisions with names. Use these exact slots:

- **Palette:** `ink` (main text), `paper` (page background), `surface` (cards/panels), `accent` (the one color that means "act"), `muted` (secondary text). Five hex codes, no more. Check that `ink` on `paper` is genuinely dark-on-light or light-on-dark — if the contrast looks weak, fix it and say why.
- **Type:** one display font and one body font, both from Google Fonts so they load free with no setup. Give the exact Google Fonts embed line. Include a fallback stack.
- **Scale:** six sizes, in rem, built on one ratio. Example on a 1.333 ratio: 0.875 / 1 / 1.333 / 1.777 / 2.369 / 3.157. State the ratio you chose.
- **Spacing:** one base unit (usually 8px) and the steps that come off it: 8 / 16 / 24 / 40 / 64 / 96. Every gap on every page uses one of these numbers and nothing else.
- **Radius, borders, shadow:** one value each, or the word "none."
- **Motion:** one duration (150-250ms) and one easing. Transforms and opacity only.

Also write the **don't list**, and put this on it by name every single time:

> Never the generic purple-to-blue AI gradient. It is the visual signature of a page nobody thought about. If a build ever reaches for `#6366f1` fading into `#a855f7`, stop and use the accent from this file instead.

Add three or four more don'ts pulled from what the references avoided.

### 4. Render a swatch preview they can actually see
A design system nobody looks at gets ignored. Write a single self-contained `index.html` preview so they can open it in a browser and see the thing. Build it under these constraints:

- One file. No build tools. No external JS libraries.
- Google Fonts is the only external resource, loaded with a normal `<link>`.
- Shows: the five color swatches with their hex codes printed on them, all six type sizes with the real font, a spacing ruler showing the six steps as stacked bars, one sample button, one sample card, and one sample headline-plus-paragraph block so they can see the pairing in real use.
- Real placeholder copy. Write actual sentences about their thing. Never lorem ipsum.
- Any icons are inline SVG.
- Fully readable with JavaScript off. Mobile-first — it must look right on a phone.
- Any animation uses transforms and opacity only. No animated blur, no noise filters, no marquees.

### 5. Show it, then take one round of reaction
Tell the user to open the preview file and give you a plain-English reaction. Not code — a feeling. "Too cold." "The headline font is trying too hard." "Love the color, hate the spacing." Make one round of edits from that, save both files again, and stop. One round is enough. They can change it later; the point is having a file at all.

## Output — save it

Write two files:

1. `~/.claude/design.md` — the system in plain markdown. Structure it exactly like this so other skills can read it reliably:

```markdown
# My Design System

## Feeling
<their one sentence>

## References
- <site> — what I took from it

## Palette
- ink: #1C1B17
- paper: #F7F4ED
- surface: #FFFFFF
- accent: #C8492B
- muted: #6B6862

## Type
- Display: Fraunces (Google Fonts) — fallback: Georgia, serif
- Body: Inter (Google Fonts) — fallback: system-ui, sans-serif
- Embed: <link href="https://fonts.googleapis.com/css2?family=Fraunces:wght@600&family=Inter:wght@400;600&display=swap" rel="stylesheet">

## Scale (ratio 1.333)
0.875rem / 1rem / 1.333rem / 1.777rem / 2.369rem / 3.157rem

## Spacing (base 8px)
8 / 16 / 24 / 40 / 64 / 96

## Details
- Radius: 4px
- Border: 1px solid ink at 12% opacity
- Shadow: none
- Motion: 180ms ease-out, transform and opacity only

## Don't
- Never the purple-to-blue AI gradient
- <3-4 more>

## How to use this
Paste into any build prompt: "Read ~/.claude/design.md and use that palette, font pairing, scale, and spacing. Follow the don't list."
```

2. `~/.claude/design-preview/index.html` — the swatch page.

Tell them both paths. Then give them the single next action, worded exactly:

> "Open `~/.claude/design-preview/index.html` in your browser. From now on, start any build prompt with: 'Read ~/.claude/design.md and follow it.'"

## Example (input → output)

**Input:** "I like the way Stripe's site looks and this coffee roaster's site. I want people to feel like I know what I'm doing. I have no idea what fonts I like."

**Output (saved to `~/.claude/design.md`):**
- **Feeling:** calm competence — clean, not corporate.
- **What the two share:** near-white background, near-black text, exactly one accent, huge headline-to-body jump, no drop shadows anywhere.
- **Palette:** ink `#161616`, paper `#FAFAF8`, surface `#FFFFFF`, accent `#B4472A`, muted `#71706B`.
- **Type:** Display = Fraunces 600. Body = Inter 400/600. Serif headline over sans body — that pairing is doing most of the work.
- **Scale:** 1.333 ratio. Headline `3.157rem`, body `1rem`. That's a 3.1x jump, which is why it reads confident.
- **Spacing:** base 8. Sections get 96 top and bottom. Nothing on the page uses a number outside the ladder.
- **Don't:** never the purple-to-blue AI gradient; no drop shadows; no stock photos of people at laptops; never more than one accent color on a screen.

And `~/.claude/design-preview/index.html` opens to five labeled color blocks, the six type sizes shown in Fraunces and Inter, a stack of spacing bars, and a sample card with a real headline and button.

## Notes / edge cases
- The beginner failure this prevents: re-deciding colors and fonts from scratch on every build, so nothing they make looks related. Deciding once is the whole point.
- If they give references that fight each other (a brutalist poster site and a soft wellness brand), name the conflict out loud and make them pick one to lead. Don't average them — averaged design is what "generic" means.
- If they hate everything you propose, that's information, not failure. Ask "what specifically feels wrong — the color, the font, or the amount of space?" One word from them is enough to redirect.
- If they already have a logo or a brand color they must keep, that color becomes `accent` and everything else gets built around it.
- Once this file exists, hand off to **make-it-designed** to apply it to something they already built, or **mobile-check** to make sure it survives on a phone.
