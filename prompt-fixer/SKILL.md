---
name: prompt-fixer
description: Paste the prompt that gave you bad output and get back the reason it failed plus the rewritten prompt to run instead. Checks the seven usual causes — too vague, three asks in one, no constraints, no format, no done-when, missing context, asking for code instead of an outcome — and hands you a fixed version. Use when the user says "this isn't what I wanted", "Claude gave me garbage", "my prompt didn't work", "fix my prompt", "why did it do that", "it ignored what I asked", "it keeps giving me the wrong thing", "rewrite this prompt", or "/prompt-fixer".
---

# Prompt Fixer — diagnose, then rewrite

You asked, you got something wrong, and it feels like the model let you down. Almost always it's a thin prompt, not a bad model. This skill finds which of seven things went missing, tells you in one line, and hands back a rewritten prompt you can run right now.

## Setup
None. This skill works out of the box.

## Steps

### 1. Collect the evidence
Ask for the prompt they used, word for word. If they've still got it, also take what came back — even a summary like "it made a purple gradient landing page with fake testimonials."

Also ask one question: "What did you actually want instead?" One sentence. That's the target the rewrite aims at.

If they only have the prompt and not the output, proceed. The diagnosis usually shows up in the prompt alone.

### 2. Say the reassuring thing first, once
Lead with: "This is a prompt problem, not a you problem. Nothing is broken and nothing was wasted." Say it once, plainly, then get to work. Beginners quit at this exact moment, and they quit because they think they're bad at this.

### 3. Run the seven checks
Go through all seven against their prompt. Mark each hit or miss. Do not stop at the first one — most bad prompts have two or three.

1. **Too vague.** Could five different people read this and picture five different results? "Make me a website" fails. The tell: no describable person, no describable outcome.
2. **Three asks in one.** Count the verbs that produce something. More than one deliverable means **One Job Rule** violation, and Claude does all of them at half depth. "Build the page and write my emails and set up my domain" is three prompts.
3. **No constraints.** Nothing said what it can't do. Without fences, output drifts to the average of everything — the generic purple gradient, the fake testimonials, the stock-photo look. Missing constraints is the single most common cause of "it looks like AI made it."
4. **No format.** They didn't say the shape of the answer, so they got an essay when they wanted a list, or five files when they wanted one.
5. **No done-when.** No finish line, so the output stops wherever the model felt like stopping, and they can't tell if it's right.
6. **Missing context Claude couldn't know.** Their price, their audience's real complaint, what already exists on their machine, the thing they tried last week. Claude cannot see any of it. This is the cause when output is technically correct but feels like someone else's business.
7. **Asked for code instead of an outcome.** They wrote "add a flexbox with a media query" or "use React." They're a director, not a typist — describing the machinery caps the result at what they happen to know. The fix is always: describe what a person should see or be able to do.

### 4. Name the primary cause
Pick the ONE that did the most damage and say it in a single sentence, in their language, tied to what they actually got back. "You got fake testimonials because nothing in your prompt told it what your business actually is — that's missing context."

List the secondary causes as short bullets underneath. Don't lecture on all seven.

### 5. Rewrite it
Produce the fixed prompt in a copy-ready block, using the 5-Part shape: CONTEXT, GOAL, CONSTRAINTS, FORMAT, DONE-WHEN.

Rules for the rewrite:
- Use their real words and real details wherever they gave them.
- Where you had to guess, guess sensibly and mark it as an assumption below the block — never invent numbers, revenue, clients, or credentials.
- If the original was three asks, rewrite only the first one and list the other two as separate prompts to run after.
- Never put code in the rewrite.

### 6. Show the diff in plain words
Two or three lines: what you added and why it will change the result. "Added a constraint against gradients and stock photos — that alone kills the AI look. Added a done-when so you'll know when to stop."

This is the teaching part. Next time they write the prompt right themselves, which is the actual goal.

## Output — save it
Create `~/briefs/` if needed. Save as `~/briefs/fixed-<short-slug>.md`.

The file holds: the original prompt verbatim, what they got, the primary cause in one line, the secondary causes, the rewritten prompt in a copy-ready block, the assumptions made, and the plain-words diff.

Tell them the path, then the one action: start a **fresh** Claude session and paste the rewritten prompt. Running a fix on top of a bad conversation drags the old wrong answer along with it.

## Example (input → output)

**Input:** "I typed 'build me a landing page for my coaching business' and it made a page with a purple gradient, three fake five-star reviews from people who don't exist, and a pricing table with three tiers I never mentioned."

**Output (saved to `~/briefs/fixed-coaching-landing-page.md`):**

**Primary cause:** Missing context. You never told it what your coaching actually is or who buys it, so it filled the gaps with a generic template — that's where the invented reviews and made-up pricing tiers came from.

**Also:** No constraints (nothing forbade gradients, fake proof, or pricing). No done-when. No format.

**Rewritten:**
```
CONTEXT: I coach recently laid-off marketing managers through their first
90 days of freelancing. One offer: a 6-week 1:1 program. I have no
testimonials yet. I have no logo. My clients find me on LinkedIn.

GOAL: Build one page that gets a laid-off marketing manager to book a free
intro call with me.

CONSTRAINTS: One self-contained index.html. No testimonials, no reviews, no
logos, no pricing table — I have none of those and I won't fake them. No
purple or blue gradients. One accent color. Mobile first.

FORMAT: A single index.html file. Google Fonts only, one display font and
one body font.

DONE-WHEN: Someone on their phone can read it in 30 seconds, know it's for
laid-off marketers, and tap one button to book a call.
```

**Assumptions:** that the intro call is free, and that the button should link to a calendar. Change either if wrong.

**What changed:** Real context replaced the template. A constraint that bans fake proof means it can't invent reviews again. A done-when means you'll know when to stop editing.

## Notes / edge cases
- The failure this prevents is a beginner concluding "AI can't do this" after one thin prompt. Say the diagnosis warmly and move fast to the rewrite.
- If they can't remember the exact prompt, work from what they got back — the shape of a wrong answer reveals what was missing.
- If the prompt is actually fine and the output was just a first draft, say so and tell them to react in plain words and run it again. Five to ten rounds is normal — that's the Build Loop, not a broken prompt.
- If they're stuck on an error message rather than a bad result, that's a different problem — hand off to **error-decoder**.
- If they're starting fresh instead of repairing something, hand off to **brief-builder**.
