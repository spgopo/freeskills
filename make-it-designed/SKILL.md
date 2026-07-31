---
name: make-it-designed
description: Take a page you already built and make it look designed instead of default, without rebuilding it. Runs a fixed polish checklist — one display font and one body font with confident size jumps, a real spacing scale, a restrained palette, hierarchy that survives a squint test — then adds exactly one signature touch so the page has a point of view. Use when the user says "make this look better", "it works but it looks bad", "make it look designed", "polish this page", "why does my site look cheap", "it looks like a template", "clean this up visually", "make it look expensive", or types /make-it-designed.
---

# Make It Designed — refine, don't rebuild

You built something and it works, but it looks like a form. The instinct is to add: more colors, more sections, more icons, a hero video. That instinct is wrong. Designed pages look designed because someone removed things until only the working parts were left, then added one deliberate detail. This runs that pass on a page you already have, and it never rebuilds from scratch.

## Setup
None. This skill works out of the box.

## Steps

### 1. Find the page and set the rule
Ask for the file path of the page. If they don't know it, look for `index.html` in the folders they've been working in and confirm with them before touching anything.

Then read the whole file and say the rule out loud, because it changes what happens next:

> "I'm refining this, not rebuilding it. Your content, your structure, and your links stay exactly where they are. I'm only changing how it looks."

Before editing, tell them: "If you hate the result, type `/rewind` and it goes back. You can't break this."

If `~/.claude/design.md` exists, read it and use that palette, font pairing, scale, and spacing instead of inventing new ones. If it doesn't exist, mention once that **design-taste** would lock those decisions permanently, then proceed with sensible choices for now.

### 2. Remove three things before you add one
Go through the page and find at least three things to delete. This is not optional and it happens before any additions. Look for:

- **Colors past the third.** Count every distinct color on the page. If there are more than five including black and white, cut down to five.
- **A second accent color.** There is one accent. The other one is decoration pretending to be meaning.
- **Drop shadows doing nothing.** A shadow should say "this floats above that." If everything has a shadow, nothing floats. Delete most of them.
- **Borders that duplicate spacing.** If a border and a big gap both separate two sections, keep the gap and drop the border.
- **Icons that repeat the words next to them.** A checkmark next to the word "included" adds nothing.
- **Repeated calls to action.** One page, one job. If there are three different buttons asking for three different things, pick one and make the others plain text links.
- **Center-aligned body paragraphs.** Centered headlines can work. Centered paragraphs are hard to read. Left-align anything over two lines.
- **Gradients that aren't doing work,** starting with the purple-to-blue one.

Show them the list of what you cut and why, in one line each.

### 3. Run the checklist
Now fix the four things that make the difference. Work in this order.

**Type — two fonts, confident jumps.**
- Exactly one display font for headlines and one body font for everything else. Both from Google Fonts. Delete any third font.
- Set six sizes on one ratio and use only those. The most common beginner mistake is timid jumps: a headline at `1.5rem` over body at `1rem` reads as an accident. Push the biggest headline to at least 2.5x the body size. On a phone, at least 2x.
- Body text between 16px and 18px. Line height 1.5-1.65 on body, 1.05-1.2 on big headlines. Headlines get tighter as they get bigger — that single change does more than any color choice.
- Line length capped around 65-75 characters (`max-width: 65ch`). Full-width paragraphs are the fastest way to look unfinished.

**Spacing — a real scale, not guesses.**
- Pick a base of 8px and use only 8 / 16 / 24 / 40 / 64 / 96. Replace every odd number on the page (13px, 22px, 35px) with the nearest step.
- Space between sections should be much bigger than space inside them. If a heading sits equally far from its own paragraph and from the section above it, the page reads as one long mush. Roughly: gaps inside a group get one step, gaps between groups get three steps.
- Generous outer margin on mobile — 20-24px minimum, never text touching the screen edge.

**Palette — restrained.**
- Five colors: text, background, surface, one accent, one muted grey. That's the whole page.
- The accent appears on under 10% of the pixels. It marks the one thing you want clicked. If the accent is on the header, three headlines, and the footer, it stops meaning anything.
- Check real contrast. Grey text on a grey background is the second most common beginner tell.

**Hierarchy — the squint test.**
- Squint at the page (or blur it in your head) until words become shapes. You should still be able to tell, in order: what this is, what it does for me, what to click.
- If everything is the same weight and size, nothing is first. Fix by size and weight, not by color.
- Exactly one thing on the screen should be the loudest. Usually the headline. Sometimes the button. Never both.

### 4. Add exactly ONE signature touch
Now, and only now, add one thing. One. It is what makes the page feel like a person made it. Pick whichever fits the page best and tell them why you picked it:

- **A hand-drawn SVG underline that draws once.** An inline SVG path under three or four words of the headline, in the accent color, with a slightly wobbly hand-drawn shape — not a straight rule. Animate it with `stroke-dasharray` / `stroke-dashoffset` so it draws itself once on load over about 700ms, then stops. It must never loop. With JavaScript off, the underline is simply there, already drawn.
- **An editorial headline treatment.** Oversized display type, one word or phrase in a contrasting style (italic serif inside a sans headline, or the accent color on two words only), set tight with a short kicker line above it in small caps or mono. Magazine cover, not landing page.
- **One "by the numbers" stat band.** A single horizontal row of three real numbers with short labels under them, sitting on the surface color, with generous space above and below. Only real numbers the user actually gave you. If they have no numbers, don't fake any — pick a different signature touch.

Rules for the touch: it appears once on the page, it uses the accent, and it is the only thing on the page doing something unexpected. Two signature touches cancel each other out.

Any motion is transforms and opacity only. No animated blur, no noise filters, no auto-scrolling marquees.

### 5. Keep the page honest
Before you're done, verify all of these on the edited file:

- Still one self-contained `index.html`. No build tools, no external JS libraries added.
- Google Fonts is the only external resource.
- The page is fully readable with JavaScript off. The signature touch degrades to a static version.
- Mobile-first: check it at 375px wide. Headline still fits, nothing scrolls sideways, the button is still easy to hit.
- Real copy everywhere. If you added any text, it says something true about their thing. Never lorem ipsum.
- Icons are inline SVG.

### 6. Show the before and after
Tell them what changed in plain words — the cuts, the four checklist fixes, and the one signature touch. Then tell them to open the page and give you one reaction in plain English. Make one round of edits from that reaction and stop.

## Output — save it

Edit the page in place at its original path. Then write a short change log to `~/design-notes/<page-name>-polish.md` containing: what you removed and why, the final font pairing with sizes, the spacing scale, the five hex codes, which signature touch you added, and one line on what to fix next if they want to keep going.

Tell them both paths, then:

> "Open the page and refresh. If anything looks wrong, describe what you see in one sentence — don't touch the code."

## Example (input → output)

**Input:** "I built a landing page for my dog-walking business. It works but it looks like a form someone made in 2009. File is at ~/dogwalk/index.html."

**Output:**
- **Removed:** the second blue, drop shadows on all six cards, a border that duplicated a 64px gap, checkmark icons that repeated the words beside them, and a "Learn more" button competing with "Book a walk."
- **Type:** DM Serif Display for headlines, Inter for body. Headline `3rem` over body `1.0625rem` — was `1.5rem` over `1rem`, which is why it read flat. Line height 1.1 on the headline, 1.6 on body, paragraphs capped at 65ch.
- **Spacing:** everything snapped to 8 / 16 / 24 / 40 / 64 / 96. Section gaps went from 30px to 96px. That single change did most of the work.
- **Palette:** ink `#1A1A17`, paper `#FBF8F1`, surface `#FFFFFF`, accent `#2F6B4F`, muted `#77756D`. Accent now appears only on the "Book a walk" button and the headline underline.
- **Signature touch:** a hand-drawn green underline under "your dog's favorite hour," drawn with an inline SVG path over 700ms on load. Doesn't loop. Sits there statically with JavaScript off.
- Change log at `~/design-notes/dogwalk-polish.md`.

## Notes / edge cases
- The beginner failure this prevents: adding more stuff to fix a page that looks bad. More stuff is almost always the cause. Removal is the fix.
- If the page is genuinely broken — content missing, layout collapsed — this is the wrong skill. Say so and fix the structure first, then come back.
- If the user asks for three signature touches, say no once and explain: the touch works because it's the only surprise. Three surprises is noise.
- If the content itself is the problem (no clear promise, no clear action), design won't save it. Point that out plainly — no amount of spacing fixes a page that doesn't say what it does.
- Run **mobile-check** afterwards to catch anything that breaks on a phone, and **design-taste** first if they want these choices locked in a file for every future build.
