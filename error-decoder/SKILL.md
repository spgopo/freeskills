---
name: error-decoder
description: Paste any error, red text, or scary message and get back what broke in plain English, whether you can ignore it, and the exact sentence to paste to Claude to fix it. You never touch code. Use when the user says "I got an error", "what does this mean", "red text", "it says something failed", "I think I broke it", "help I'm stuck", "this looks bad", "is this serious", "can I ignore this", "it won't run", "something went wrong", or "/error-decoder". Also fire when someone pastes a wall of technical text with no question attached.
---

# Error Decoder — translate it, then hand you the fix sentence

Red text stops beginners cold. Most of it isn't a disaster — a lot of it is a warning nobody needs to act on. This skill reads the error, tells you what broke and how bad it is, and gives you one sentence to paste back to Claude. You never open a file or edit a line.

## Setup
None. This skill works out of the box.

## Steps

### 1. Calm it down first, in two lines
Before any analysis, say two things:
- "Errors are normal. Every single person building anything sees these constantly. They are not a sign you did something wrong."
- "Nothing is permanently broken. `/rewind` puts your project back the way it was before the last change."

Say it once, plainly. Then work. Do not repeat the reassurance in every paragraph — that reads as condescending.

### 2. Get context around the error
Ask for the error text if they haven't pasted it, plus two quick things:
- "What did you just ask Claude to do right before this?"
- "Is the thing still working, or did it stop?"

That second question matters more than the error text. A red warning while the page still loads fine is a completely different situation from a page that went blank.

### 3. Classify how bad it is
Put it in exactly one of four buckets and say the bucket by name:

- **Noise.** A warning, a deprecation notice, a version complaint, an audit message. Nothing to do. The thing works. Ignore it and keep going.
- **Cosmetic.** Something looks wrong but the project runs. A missing image, a font that didn't load, a broken style. Fixable later, doesn't block tonight.
- **Blocked.** The thing won't run or won't load until it's fixed. This is the normal case and it's usually one specific missing piece.
- **Rewind it.** The last change made things worse in a tangled way. Don't debug it — undo it and take a different run at it.

Say the bucket in one sentence with the reason: "This is Noise — it's a version warning from a tool, and your page is loading fine."

### 4. Translate the error into plain English
Three short lines, no jargon:
- **What broke:** the thing that didn't work, in kitchen-table words. "It tried to open a file that isn't there."
- **Why:** the likely reason, in one clause. "The file got renamed or was never created."
- **What it isn't:** kill the fear they're carrying. "This did not delete anything. Your other files are untouched."

If a technical term must appear because it's in the error, define it in one short clause the first time. "A port — the numbered door your site uses on your computer — is already being used by something else."

### 5. Hand them the exact fix sentence
This is the deliverable. One sentence they copy and paste back to Claude, written the way a director talks: describe the symptom, not the repair.

Good shape: what they observed + where + what they expected.
- "When I open the page, it's completely blank and the terminal says 'Cannot find module express'. It was working before you added the contact form. Fix it."
- "The site loads but the header image doesn't appear, and there's a 404 for /images/hero.jpg. Find the image or use a different one."

Never write a sentence that tells them to edit a file, install something manually, or run a command they don't understand. If a command is genuinely needed, the fix sentence asks Claude to run it, not them.

For the **Rewind it** bucket, the deliverable is different: tell them to type `/rewind` (or press Esc twice with an empty input box), pick the checkpoint from before the change, then re-ask for the thing they wanted in a smaller step.

### 6. Give the one-line prevention
One sentence on how to make this less likely next time. Usually it's smaller steps, or a checkpoint before a big change. Keep it to one line — this isn't a lesson.

## Output — save it
Create `~/claude-errors/` if needed. Save as `~/claude-errors/<date>-<short-slug>.md`, for example `~/claude-errors/2026-07-30-blank-page.md`.

The file holds: the error text verbatim, the bucket, the three plain-English lines, the exact fix sentence in a copy-ready block, and the one-line prevention.

Tell them the path, then the single next action: copy the fix sentence and paste it to Claude. Nothing else.

Mention once that this folder becomes their own troubleshooting log — when the same error shows up in three weeks, they already have the answer.

## Example (input → output)

**Input:** "I asked Claude to add a contact form and now my page is just white. There's a bunch of red stuff that says `Error: ENOENT: no such file or directory, open './components/ContactForm.jsx'`"

**Output (saved to `~/claude-errors/2026-07-30-blank-page.md`):**

**How bad:** Blocked. The page won't load until this one thing is sorted. It is a single missing file, not a broken project.

**What broke:** Your page tried to load a contact form file that isn't on your computer.

**Why:** Claude wrote the line that uses the form but the form file itself never got created, or it got saved somewhere else.

**What it isn't:** Nothing was deleted. Your page, your text, and your styles are all still there. The white screen is just the page refusing to start.

**Paste this to Claude:**
```
My page is completely white now. The terminal says:
"Error: ENOENT: no such file or directory, open './components/ContactForm.jsx'"
This started right after you added the contact form. Create the missing
file so the page loads again, then show me the form.
```

**Next time:** Ask for one change at a time, and say "commit this as a checkpoint" when something works.

## Notes / edge cases
- The failure this prevents is a beginner quietly abandoning a project because red text felt like proof they're not cut out for this. Tone matters as much as accuracy here.
- Never tell them to edit code, open a config file, or run a command they don't understand. If it needs doing, Claude does it — that's the arrangement.
- If the error text is huge, find the first line that names a real thing (a file, a port, a package) and work from that. The rest is usually the same failure echoing.
- If they can't paste the error, ask them to describe what they see on screen. "The page is blank" is enough to work with.
- If nothing they try works after two rounds, stop debugging and say `/rewind` outright. Undoing is faster than untangling, and it teaches the right instinct.
- If they want to stop being scared of this happening at all, hand off to **safety-net**. If they don't understand the file the error names, hand off to **explain-this**.
