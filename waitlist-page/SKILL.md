---
name: waitlist-page
description: Build a one-page "coming soon" that collects emails before the thing exists, so you find out if anyone wants it before you spend three months building it. One promise, one field, one button, an honest date, and a real place the emails land — all free, no backend. Use when the user says "build a waitlist page", "coming soon page", "collect emails before I build", "I want to see if anyone wants this", "landing page for an idea", "pre-launch page", "validate my idea", "early access signup", "should I build this first", or types /waitlist-page.
---

# Waitlist Page — proof of demand before you build

The expensive mistake is building for three months and then finding out nobody wanted it. The cheap version is one page, up tonight, that says what the thing is and asks for an email. Twenty people who typed their email address is real information. Twelve friends saying "cool idea" is not. This builds that page, puts it somewhere real, and tells you exactly where the emails land.

## Personalization
This skill works in *your* brand voice. Before running, load the brand profile at `~/.claude/brand-profile.md`.
- If it doesn't exist, run the **personalize** skill first (or just tell me your name, niche, offer, and audience — I'll create it).
- If a field this skill needs is blank, I'll ask one or two quick questions and save the answers back to the profile so you only answer once.
- Never invent facts or results about the user — use only what's in the profile, or ask.

## Steps

### 1. Get the promise, and make it specific
Read the brand profile for who they serve and what they do. Then ask exactly four questions in one message:

1. "What is the thing, in one sentence a stranger would understand?"
2. "Who is it for, specifically? Not 'small businesses' — 'solo house cleaners with 10-40 clients'."
3. "What's the one thing it gets them that they can't get easily today?"
4. "When do you honestly think it'll be ready? A rough month is fine. A lie is not."

Then write the promise line. This is the whole page. Rules:
- Name the person and the outcome. "A booking page for solo house cleaners that stops the back-and-forth texting" beats "the future of scheduling."
- Under 15 words if you can.
- No hype adjectives. If the promise needs an adjective to sound good, the promise is weak.
- Test it: would someone who has this exact problem stop scrolling? If not, rewrite it with a more specific person.

Give them three versions of the promise line and make them pick one. Picking is faster than writing.

### 2. Decide where the emails actually land — before building the page
This is the step people skip, and then the emails go nowhere. Give them these three free options, say what each costs them in effort, and make them pick one:

- **Google Form (zero signup if they have Gmail, best default).** They make a Google Form with one email field, then the page's button links straight to it, or the page posts to the form's URL. Emails land in a Google Sheet they already own. Free forever, no limits worth worrying about. Downside: if the button just links out, the visitor leaves the page.
- **Formspree free tier (one-click signup, form stays on the page).** They sign up free, get a form endpoint URL that looks like `https://formspree.io/f/xxxxxxx`, and paste it in. The form submits without leaving the page and emails go to their inbox. Free tier covers roughly 50 submissions a month, which is plenty for finding out if an idea has legs. Downside: one signup.
- **Plain `mailto:` (nothing to set up, weakest).** The button opens the visitor's email app with a pre-filled message. No signup, no account, works instantly. Downside: many people won't finish it, so treat the count as a floor, not a real number.

If they don't want to decide right now, build it with the `mailto:` version and leave a clearly commented one-line slot at the top of the form code where a Formspree or Google Form URL gets pasted later. Tell them the exact line to swap.

Whatever they pick, the page also saves every submitted email to `localStorage` as a backup so nothing is lost while they're testing.

### 3. Write the five pieces of copy
A waitlist page has five pieces and nothing else. Write all five in their voice from the profile.

1. **The promise line.** The one they picked. This is the headline.
2. **One clarifying sentence under it.** Says who it's for and what it replaces. One sentence. Not a paragraph.
3. **The one field.** Email. Label it plainly: "Email". Placeholder: `you@example.com`. Never ask for name, company, phone, or "what's your biggest challenge." Every extra field cuts signups, and none of those answers change what they build.
4. **The button.** Says what happens, not "Submit." Good: "Tell me when it's ready." "Put me on the list." Bad: "Sign up." "Get started."
5. **What happens next, honestly.** One short line directly under the button. Something like: "I'll email you once when it's ready — around March. No other emails. That's it." This line raises signups more than anything else on the page, because the real fear is getting spammed.

Optionally, one short block of three or four lines saying what the thing will do — but only if the promise genuinely needs it. Most don't.

Never invent numbers. No "join 500 others" unless 500 others actually joined. A fake counter on a page with four signups is the fastest way to lose the four.

### 4. Build the page
Build one file. Bake in every one of these:

- One self-contained `index.html`. No build tools, no external JS libraries, no frameworks.
- Google Fonts is the only external resource. One display font for the promise line, one body font for everything else.
- Restrained palette: one accent plus neutrals. **Never** the generic purple-to-blue AI gradient. If `~/.claude/design.md` exists, read it and use that palette, font pairing, and spacing instead.
- Mobile-first. Build for a 375px-wide phone and let it grow. The promise line must fit without a horizontal scrollbar. The email field and button are full width on mobile and at least 48px tall.
- **Fully readable and usable without JavaScript.** The headline, the promise, and the form all work with scripts off. If they picked Formspree or Google Form, the plain HTML `<form action=... method="post">` handles it with no script at all. JavaScript only adds the nice touches on top.
- Animate with transforms and opacity only. One quiet entrance on the promise line at most. No animated blur, no noise filters, no auto-scrolling marquees, nothing that loops forever.
- Real placeholder copy — the actual sentences from step 3. Never lorem ipsum.
- Any icons are inline SVG.
- One job, one page: one call to action, no navigation bar, no footer links, no social icons pulling people away. Every link that isn't the button costs signups.
- After a successful submit, swap the form for a short thank-you line in place — no page reload, no popup. With JavaScript off, the form's own action handles it.
- Include the `<meta name="viewport" content="width=device-width, initial-scale=1">` tag.
- Set a real `<title>` and a one-line meta description, so the link looks right when someone texts it.

### 5. Get it in front of a stranger
An unshipped page proves nothing. Ugly-but-live beats pretty-but-local. Tell them:

- Open the file in their browser first and check it on a phone-sized window.
- To put it online free: drag the folder onto Vercel's free tier, or push the folder to a GitHub repo and turn on GitHub Pages. Both give a real URL they can text to someone.
- Then send it to five people who actually have the problem. Not five friends. Five people with the problem.
- What to watch: do they sign up without asking a clarifying question? If they have to ask "wait, what is this?", the promise line is the thing to fix, not the design.

Set the honest bar out loud: if 20 of the right people see it and fewer than 3 sign up, that's a real answer and it saved them three months. Rewrite the promise and send it again before writing a line of the product.

## Output — save it

Write the page to `~/sites/<slug>-waitlist/index.html` where `<slug>` is a short name for the idea.

Also write `~/sites/<slug>-waitlist/notes.md` with: the promise line they picked and the two they didn't, who it's for, where the emails land plus the exact line to swap if they change it later, the honest date, the five people they plan to send it to, and the decision rule (how many signups means build it).

Tell them both paths, then:

> "Open `~/sites/<slug>-waitlist/index.html` in your browser. If it looks right, put it online free and send the link to five people who actually have this problem — today, not after more edits."

## Example (input → output)

**Input:** "I want to build an app that helps dog groomers manage their appointments. I've been thinking about it for months. Not sure if anyone needs it."

**Output (saved to `~/sites/groomer-waitlist/index.html`):**

- **Promise line:** "Stop losing grooming appointments in your text messages."
- **Clarifying sentence:** "A simple booking page built for solo dog groomers. Clients pick a slot, you stop playing phone tag."
- **Field:** one email input, labeled "Email."
- **Button:** "Tell me when it's ready."
- **What happens next:** "I'll email you once when it's live — I'm aiming for March. Nothing else, ever."
- **Emails land:** Formspree free tier, endpoint pasted into the form's `action`. Backup copy saved to `localStorage`.
- **Look:** cream background, near-black text, one deep green accent on the button only. Fraunces headline over Inter body. Full-width 52px-tall button on mobile. Works with JavaScript off.
- `notes.md` records the decision rule: "20 groomers see it. Under 3 signups means the promise is wrong — rewrite and resend before building anything."

## Notes / edge cases
- The beginner failure this prevents: three months of building something nobody asked for. The page takes one night. Do the page first.
- If they insist on collecting a name, phone number, or a survey question, push back once: every field costs signups, and none of those answers change what they build. If they still want it, add name only.
- If they have no honest date, write "I don't have a date yet — I'll email you the moment I do." Honest and vague beats a made-up month.
- If the promise line takes more than one sentence to explain, the idea isn't clear enough yet. Hand off to **positioning-filter** before building the page.
- After it's live, run **mobile-check** on it — most of the people they text the link to will open it on a phone.
