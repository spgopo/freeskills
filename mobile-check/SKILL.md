---
name: mobile-check
description: Check a page you built the way a real person on a phone would actually see it, and get back a numbered fix list ordered by how much each problem costs you. Catches tiny text, buttons too small to tap, things that slide sideways off the screen, images that blow out the layout, and a main button nobody can reach with a thumb. Each fix comes with the exact sentence to paste back to Claude. Use when the user says "check this on mobile", "does my site work on a phone", "it looks broken on my phone", "why is my page sideways", "mobile version is messed up", "test my page on mobile", "my text is tiny on my phone", or types /mobile-check.
---

# Mobile Check — see your page the way most people will

You built it on a laptop. Most of the people who visit it will be on a phone, one-handed, on a slow connection, half-distracted. A page that looks fine at 1440px wide can be unusable at 375px, and you'd never know because you never looked. This reads your page, finds the things that break on a phone, and hands back a numbered list ordered by how badly each one hurts — with the exact sentence to paste back so Claude fixes it.

## Setup
None. This skill works out of the box.

## Steps

### 1. Get the page and set the frame
Ask for the file path. If they don't know, find the `index.html` they've been working on and confirm before reading.

Read the whole file — HTML, the CSS inside it, and any inline JavaScript. Then set the frame out loud:

> "I'm reading this as a phone at 375 pixels wide — that's an average iPhone. Everything below is what breaks at that size."

If they have a live URL and a browser tool is available, open it at 375x812 and look. If not, read the code carefully — nearly every mobile failure is visible in the CSS.

### 2. Run the seven checks
Go through these in order. For each, list every specific offender with the element and the value you found.

**1. Sideways scroll (the worst one).** If the page slides left and right, everything else is a footnote. Look for: fixed pixel widths larger than 375 (`width: 600px`), `min-width` on containers, tables, long unbroken strings like URLs or emails, `100vw` combined with padding, negative margins, absolutely positioned elements pushed past the right edge, and images without `max-width: 100%`. Also check for a missing `<meta name="viewport" content="width=device-width, initial-scale=1">` — without that line the whole page renders zoomed out and tiny, and it is the single most common cause.

**2. Tap targets.** Anything you tap — buttons, links in a row, nav items, form controls, icon buttons — needs to be at least 44x44 pixels of actual tappable area, with at least 8px of space between it and the next tappable thing. Flag: small icon-only buttons, text links packed in a tight list, tiny close buttons, and checkboxes at default size. A person's thumb is about 10mm wide and they are not aiming carefully.

**3. Text too small.** Body text under 16px. This is not a style opinion — under 16px, phones may zoom the page when someone taps a form field, which yanks the layout sideways. Flag every font-size under 16px on body copy, and anything under 14px anywhere. Also flag line lengths that run edge to edge with no breathing room, and line-height under 1.4 on body text.

**4. Images pushing the layout.** Every image needs `max-width: 100%; height: auto;`. Flag fixed-width images, background images with fixed sizes, images with no `width`/`height` attributes (which makes the page jump while loading), and any image file that's clearly huge for a phone. Also check that anything with text baked into it is still legible small — usually it isn't.

**5. Thumb reach on the main action.** Where is the one button you want tapped? On a phone held one-handed, the easy zone is the bottom two-thirds of the screen, and the hardest place to reach is the top corners. Flag: a primary button only in the header, a primary button that only appears after a long scroll with no repeat, and any critical action sitting in a top corner. The fix is usually to repeat the main button lower down, or to pin it to the bottom.

**6. Does it read with JavaScript off?** Turn JS off in your head and re-read the page. Flag anything that only appears via script: content revealed by an accordion or tab, images that lazy-load through JavaScript with no fallback, animations that start elements at `opacity: 0` and never restore them if the script fails, and menus that don't open. The headline, the offer, and the main link must be there without any script running at all.

**7. Everything else that costs real visitors.** Multi-column grids that never collapse to one column. Horizontal padding under 16px so text touches the screen edge. Sticky headers eating more than about 15% of the screen height. Hover-only interactions — phones have no hover, so anything that only appears on hover is invisible. Forms with the wrong keyboard (an email field should use `type="email"`, a phone field `type="tel"`). Fixed-position elements covering content. Font sizes set in `vw` units that go unreadable at small widths.

### 3. Rank by damage, not by effort
Sort every problem you found into this order and number them 1, 2, 3...:

1. **Kills the page** — sideways scroll, missing viewport tag, content invisible without JS, the main button unreachable or absent.
2. **Costs you the visitor** — tap targets too small, body text under 16px, images blowing out the layout, forms that are painful to fill.
3. **Looks unfinished** — tight padding, columns that didn't collapse, weak line height, hover-only nice-to-haves.

Do not pad the list. If you found four real problems, give four. A fake list teaches them to ignore real ones.

### 4. Write the paste-back sentence for each fix
This is the part that makes the skill useful. For every numbered problem, write one plain-English sentence the user can copy and paste straight back to Claude. It describes the symptom and the outcome — never the code. That's the beginner move: describe what you saw, don't try to edit CSS.

Good paste-back sentences:
- "On my phone the page slides left and right. Make it so nothing scrolls sideways at 375px wide."
- "The 'Book now' button is too small to tap on a phone. Make every button and link at least 44px tall with space between them."
- "The body text is too small to read on a phone. Set body text to at least 16px with line height 1.6."
- "My hero image runs off the side of the screen on a phone. Make all images shrink to fit their container."
- "The only 'Get started' button is at the very top. Add the same button again near the bottom of the page so I don't have to scroll back up."
- "Add the mobile viewport tag to the page head so it doesn't render zoomed out on phones."

Bad ones — never write these: anything with a selector, a property name, or a pixel value they'd have to understand.

### 5. Tell them the one to do first
End with the single highest-value fix and nothing else. One task per prompt. Tell them to paste that one sentence, look at the page again, then come back for the next one. Fixing all eight in one prompt is how a working page turns into a broken one.

Remind them: `/rewind` undoes any change, so trying a fix costs nothing.

## Output — save it

Write the full report to `~/mobile-checks/<page-name>-<date>.md` with:
- The page path and the width you checked.
- The numbered problem list, each with: what's wrong, where it is in the page, why it costs them, and the paste-back sentence in a copyable block.
- A short "already good" list — the things that passed. People need to know what not to touch.
- The one fix to do first.

Tell them the path, then:

> "Copy fix #1 and paste it as your next message. Then look at the page again and come back for #2."

## Example (input → output)

**Input:** "I made a page for my cleaning business and my sister says it looks weird on her phone. It's at ~/cleaning/index.html."

**Output (saved to `~/mobile-checks/cleaning-2026-07-30.md`):**

**1. The page renders zoomed out and tiny.** There's no viewport tag in the head, so phones render it at desktop width and shrink everything. This is why your sister said it looks weird — it's one missing line.
> "Add the mobile viewport tag to the page head so it doesn't render zoomed out on phones."

**2. The page scrolls sideways.** The pricing table is set to `width: 720px`, which is wider than a phone screen, so the whole page drags left and right.
> "My pricing table makes the page scroll sideways on a phone. Make it stack into a simple list on small screens instead of a wide table."

**3. The "Get a quote" button is too small to tap.** It's 28px tall and sits 4px from the phone number link, so people will hit the wrong one.
> "The 'Get a quote' button is too small to tap on a phone. Make every button and link at least 44px tall with 12px of space between them."

**4. Body text is 14px.** Hard to read, and it makes iPhones zoom in when someone taps the form.
> "The body text is too small to read on a phone. Set body text to at least 16px with line height 1.6."

**Already good:** images have `max-width: 100%`, the page reads fine with JavaScript off, the columns collapse to one on small screens, and the phone number uses `type="tel"`.

**Do first:** #1. It's one line and it may fix half of what she saw.

## Notes / edge cases
- The beginner failure this prevents: building on a laptop, testing on a laptop, and shipping something most visitors literally cannot use.
- If the page has no viewport meta tag, that is always #1 and you should say plainly that several other problems on the list may vanish once it's added.
- If they can't give a file path but have a live URL, work from the URL. If they have neither, ask for a screenshot from their actual phone and read that.
- If the page is a single paragraph of text with no styling, say it's fine and don't invent problems. An honest short report builds trust in the long ones.
- If the page is ugly rather than broken, that's a different job — hand off to **make-it-designed**.
