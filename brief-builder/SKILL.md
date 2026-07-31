---
name: brief-builder
description: Turns a vague ask into a surgical 5-Part Brief you can paste straight into Claude and get the right thing back on the first try. Fills in CONTEXT, GOAL, CONSTRAINTS, FORMAT, and DONE-WHEN, then gives you a one-sentence compressed version for quick asks. Use when the user says "write me a prompt", "how do I ask for this", "turn this into a prompt", "make my prompt better", "I don't know how to describe what I want", "help me explain this to Claude", "brief for", "what should I type", or "/brief-builder". Also use before any real build, so they ask properly the first time.
---

# Brief Builder — vague in, surgical out

Beginners ask Claude for "a website" and get a website that isn't theirs. The gap isn't skill, it's specificity. This skill takes whatever you say, however messy, and turns it into a 5-Part Brief — CONTEXT, GOAL, CONSTRAINTS, FORMAT, DONE-WHEN — that you paste in and run. Same frame works for a landing page, an email, or a spreadsheet.

## Setup
None. This skill works out of the box.

## Steps

### 1. Take the ramble and find the deliverable
Let them describe it in their own words. Do not correct their language. Read it back as one sentence: "So the thing that exists at the end is ___ ." Get a yes before you write anything.

If they named three things, stop. **One brief, one deliverable.** Pick the one they'd do first and note the others at the bottom as "next briefs."

### 2. Fill CONTEXT — what's true right now
This is the part beginners skip, and it's why output feels generic. Claude cannot see their life. Ask only for what changes the answer:
- Who is this for? Not "everyone" — one describable person.
- What already exists? Files, a site, a doc, nothing at all.
- What do they know that Claude can't guess? Their offer, their price, their audience's actual complaint, the tool they're stuck with.

Write CONTEXT as 2-4 plain sentences of fact. No goals in here.

### 3. Fill GOAL — the one thing this must accomplish
One sentence. Starts with a verb. Names the outcome, not the code.

Kill these patterns on sight:
- Code instead of outcome: "add a flexbox container" → "put the three cards side by side on desktop."
- Two goals hiding as one: "build a site and write my emails" → split. **One Job Rule.**
- A feeling with no test: "make it professional" → "make it look like a $200/hr consultant made it, not a template."

### 4. Fill CONSTRAINTS — what it can't do
Constraints are what make output specific. Get 3-5. Prompt them with:
- Length, size, or budget limits.
- Things they hate — a tone, a look, a word, a color.
- Technical fences: one file, no signups, works on a phone, no paid tools.
- What to leave out entirely.

If they can't name any, offer two and let them react. People are much better at rejecting than inventing.

### 5. Fill FORMAT — the shape of the answer
Say exactly what comes back: a single `index.html` file, a bulleted list of ten, a table with three columns, a 200-word email, a folder of three files. Include where it should be saved if that matters.

Vague format is why people get essays when they wanted a list.

### 6. Fill DONE-WHEN — how you know it's finished
The line most people never write, and the one that stops endless tweaking. It must be checkable by looking at something, not by feeling satisfied:
- "A stranger on their phone can read it and tap one button to email me."
- "The page loads with no errors and the headline names my audience."
- "The list has ten items, none about pricing."

If their done-when contains "good," "nice," or "professional," rewrite it until it's observable.

### 7. Write both versions
**Long form** — the five labeled parts, in a copy-ready block.

**Compressed form** — one sentence they can use for small asks:
> "Given [context], do [goal], without [constraint], formatted as [format] — done when [done-when]."

Teach the compressed line explicitly. It's the one they'll use forty times a week without opening this skill.

Then show a short **before/after**: their original ramble on one side, the brief on the other, so they see what changed.

## Output — save it
Create `~/briefs/` if needed. Save as `~/briefs/<short-slug>.md` — slug from the deliverable, like `landing-page.md` or `client-welcome-email.md`.

The file holds: the original ask verbatim, the 5-Part Brief in a copy-ready block, the compressed one-liner, and any "next briefs" that got parked.

Tell them the path, then tell them the one action: paste the long-form block into a fresh Claude session and let it run. If the result is wrong, they change ONE part of the brief and run it again — that's the loop, not a failure.

## Example (input → output)

**Input:** "I want a page for my dog-walking thing so people can book me. Nothing fancy."

**Output (saved to `~/briefs/dog-walking-page.md`):**

*Before:* "I want a page for my dog-walking thing so people can book me."

*After:*
```
CONTEXT: I walk dogs in Oakland, mostly for people who work in an office
and can't get home midday. I charge $28 a walk. I have no website, just a
phone number. My customers find me through neighbors.

GOAL: Build one page that gets a busy dog owner to text me to book a walk.

CONSTRAINTS: One self-contained index.html file, no signups, no booking
software. Must be readable on a phone with one hand. No stock photos of
smiling models. Don't mention prices for packages I don't offer yet.

FORMAT: A single index.html file, mobile first, one accent color, Google
Fonts only.

DONE-WHEN: A neighbor can open the link on their phone, understand in five
seconds that I walk dogs in Oakland, and tap one button that opens a text
message to me.
```

*Compressed:* "Given I'm a solo dog walker in Oakland with no site, build a one-page site that gets a busy owner to text me, without booking software or stock photos, as one mobile-first index.html — done when a neighbor can tap one button to text me."

*Next briefs:* a flyer for the block, a follow-up text for repeat clients.

## Notes / edge cases
- The failure this prevents is asking for output and blaming the model for the answer. Thin brief, thin result.
- If they give you two sentences and no detail, don't run an interview. Fill in sensible defaults, mark them clearly as assumptions at the bottom, and let them correct one. Momentum beats a questionnaire.
- If the deliverable is genuinely huge — a whole app, a whole course — write the brief for the first shippable slice only, and list the rest as next briefs.
- Never put code in a brief. They describe the outcome, Claude picks the how. That's the whole arrangement.
- If they already ran a prompt and got something bad, don't rewrite from scratch — hand off to **prompt-fixer**, which diagnoses why it failed first.
