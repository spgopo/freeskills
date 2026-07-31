---
name: landing-page
description: Build a one-page site with a single job — collecting an email or a booking — with a headline, three proof points, one form, one button, and an FAQ that kills the biggest objection. Includes a working free form setup so the emails actually reach you. Use when the user says "build me a landing page", "/landing-page", "I need a page to collect emails", "opt-in page", "a page for my free guide", "waitlist page", "lead magnet page", "signup page", "I want people to give me their email", "a page for my newsletter", or "somewhere to send people from Instagram".
---

# Landing Page — one page, one job, one button

Most beginner pages ask for too much. Follow me, and buy this, and read my blog, and join the list. A page that asks for two things gets neither. This builds one page whose only job is to capture a lead, with a form that actually delivers to your inbox, saved as a single file you can put online in minutes.

## Personalization
This skill works in *your* brand voice. Before running, load the brand profile at `~/.claude/brand-profile.md`.
- If it doesn't exist, run the **personalize** skill first (or just tell me your name, niche, offer, and audience — I'll create it).
- If a field this skill needs is blank, I'll ask one or two quick questions and save the answers back to the profile so you only answer once.
- Never invent facts or results about the user — use only what's in the profile, or ask.

## Steps

### 1. Name the one job out loud
Ask: "When someone leaves this page, what is the one thing they did?" Push until it's a single action:
- Gave me their email for the free guide.
- Booked a call.
- Joined the waitlist.

Then say the rule plainly: **one job per page.** Everything that doesn't serve that job comes off. No nav bar, no social icons, no "check out my other stuff," no second button that goes somewhere else. If they resist, ask which one they'd give up if they could only keep one — that's the job.

Also collect from the profile or by asking:
- **Who it's for** in specific words (not "entrepreneurs" — "people who quit their job last month and have no clients yet").
- **The one outcome** they get. What's different about their life after.
- **Three proof points** — real ones. Things they've done, results they can name, or concrete facts about what's inside. If they have no proof yet, use three concrete specifics about the thing itself instead. Never invent a testimonial or a number.
- **The top objection.** The reason someone reads this and closes the tab. Usually: is this actually free, how long does it take, will you spam me, is this for someone at my level.

### 2. Write the copy before building anything
Fill this exact skeleton in their voice. Short sentences. Concrete, not clever.

- **Headline** — promises ONE outcome. Not what it is, what they get. "Get your first paying client in 30 days" beats "The Client Acquisition System."
- **Subhead** — names who it's for and what the thing is. "A free 12-page guide for freelancers who've never sold anything."
- **Three proof points** — one line each, scannable, no paragraphs.
- **The form** — as few fields as possible. Email only unless they truly need a name. Every extra field costs signups.
- **The button** — says what happens next in first person or plain verb. "Send me the guide." Not "Submit."
- **FAQ block** — three to four questions max, and the first one kills the top objection head-on.
- **One line under the button** telling them what happens after: "You'll get it in your inbox in about a minute. No spam, unsubscribe anytime."

Read the copy back and cut anything that doesn't push toward the one job.

### 3. Set up where the emails go
The form has to actually deliver somewhere or the page is decoration. Give them these two options in one clause each and let them pick:

- **Formspree (recommended)** — free, no code: sign up at formspree.io, create a form, paste the URL it gives you into the form's `action` and you get submissions by email. Ask them for the URL and wire it in.
- **mailto fallback** — zero signup: the button opens their visitor's email app with a pre-filled message to your address. Uglier and fewer people finish it, but it works right now with nothing to set up.

If they don't want to stop and sign up, build with the mailto fallback and leave a clearly marked one-line comment in the file where the Formspree URL goes later. Never leave a form that silently goes nowhere.

### 4. Build the page
One self-contained `index.html`:
- No build tools, no external JavaScript libraries. Google Fonts is the only outside resource — one display font, one body font, chosen to match their brand.
- One accent color plus neutrals. Never the purple-to-blue AI gradient. The accent is used for exactly one thing: the button.
- Animation with transforms and opacity only, used sparingly. No animated blur or noise, no auto-scrolling marquees.
- Fully readable and fully submittable with JavaScript off — a plain HTML form post, not a JS handler. Mobile-first; assume a phone in one hand.
- Real copy from step 2, never lorem ipsum. Inline SVG for any icon. Photos only if they supplied one or approved a free Unsplash image.
- Order down the page: headline, subhead, form + button, three proof points, second button, FAQ, one-line footer. Form high on the page AND one repeat of the button after the proof.

Save to `~/sites/<slug>/index.html`.

### 5. Preview, then run the loop
Open it:

```bash
open ~/sites/<slug>/index.html
```

Ask: "Read it like a stranger on their phone. What's the first thing that makes you hesitate?" Fix one thing at a time in plain English. Five to ten rounds is normal.

Run this check every couple of rounds and say it out loud: **is there anything on this page competing with the one job?** If yes, cut it.

Then test the form once for real — submit it themselves and confirm the email lands. A page that looks perfect and swallows leads is worse than an ugly one that works.

### 6. Save the note file and hand off
Write `~/sites/<slug>/NOTES.md` with the one job, the headline, where the form delivers, and the one-line next step.

Close with: "Run **deploy-it** to get this on a real link, then put that link in one place people already see you today."

## Output — save it
- `~/sites/<slug>/index.html` — the landing page, one file, working form.
- `~/sites/<slug>/NOTES.md` — the one job, the headline, the form destination, and tomorrow's next step.

State both paths. Single next action: run **deploy-it**, then paste the link in their bio or send it to their list.

## Example (input → output)
**Input:** "I made a free checklist for people leaving their job to freelance. I want a page where they can get it."

**Output (saved to `~/sites/freelance-checklist/index.html`):**

- **Headline:** "Know exactly what to set up before you quit."
- **Subhead:** "A free 2-page checklist for people leaving a salary to freelance in the next 90 days."
- **Form:** one email field. Button: **"Send me the checklist."** Under it: "It arrives in about a minute. No spam, unsubscribe anytime."
- **Proof:** *Written from 4 years of doing it wrong first* / *Covers taxes, savings runway, and your first three clients* / *Two pages, not a 40-page ebook*
- **FAQ:** "Is this actually free?" — "Yes. No card, no call, no upsell email chain." Plus two more.
- Form posts to their Formspree URL. Nothing else on the page — no nav, no social links, no second offer.

## Notes / edge cases
- The failure this prevents: a page with five links where the visitor picks none. If the user insists on adding a second call to action, ask which one they'd delete if forced. That answer is the page.
- If they have no proof yet, use concrete facts about the thing (length, format, what's covered) instead of results. Never write a testimonial they didn't get.
- If they can't name the top objection, ask what a friend would say if they sent it to them right now. That's usually it.
- If the form URL isn't set, say so out loud at the end — don't let them ship a page that quietly loses every signup.
- Hand off: **deploy-it** to publish. **offer-builder** if the thing they're giving away is unclear. **sales-page** if they're actually trying to sell, not collect. **hooks** if the headline keeps coming out flat.
