---
name: session-wrapup
description: Close out a build session properly so reopening tomorrow takes five minutes instead of thirty. Summarizes what actually changed, what's working, what's half-finished, and writes ONE line for tomorrow's first move — then prompts you to save a checkpoint before you close the laptop. Use when the user says "wrap up", "I'm done for tonight", "end of session", "log what we did", "save where I got to", "what did we do today", "I'm stopping here", "before I close this", "session wrapup", or types /session-wrapup.
---

# Session Wrap-Up — end the night so tomorrow starts fast

You build for 90 minutes, close the laptop, and come back two nights later with no idea where you left off. You spend half the next session re-reading files and re-explaining the project. That lost half hour is why builds die.

This is the last ten minutes of the night. It writes down what changed, what's working, what's half-done, and one single line telling tomorrow-you exactly where to pick up. One line. Not a to-do list.

## Setup
None. This skill works out of the box.

## Steps

### 1. Look at what actually happened
Don't ask the user what changed — they were watching loosely and they'll under-report. Find out yourself.

Run `pwd` to confirm the project, then check what changed: if the folder is a git repo, run `git status` and `git diff --stat`. If it isn't, list the files and check what was modified today.

Also read back over this session for what you did. Then state it in plain language, three to six lines, no jargon: "The page now has a headline, three cards, and a working contact button. The photos are still placeholders."

If the user starts the session with this skill and there's no history to read, ask them one question instead: "What did you change tonight?"

### 2. Separate working from half-done
Sort everything into two honest piles. Be strict — this list is only useful if it's true.

- **Working:** things you or the user actually looked at and saw behave correctly. If it wasn't opened and checked, it doesn't go here.
- **Half-done:** started and not finished, or finished and not checked. Say what's missing in one clause each.

If something is half-done and the user thinks it's finished, say so now. Finding out tomorrow costs more.

### 3. Note anything that surprised you
One or two lines, only if there's something real: a decision that got made, a thing that turned out harder than expected, a choice they should remember. Skip this if nothing notable happened. Don't pad it.

### 4. Write the one line for tomorrow
This is the most valuable line in the file, so get it right. It must be:

- **One move, not a list.** If you write three things, tomorrow-you reads all three and starts none.
- **Specific enough to start cold.** "Keep working on the page" is useless. "Replace the three placeholder photos with real ones and check it on a phone" is a starting gun.
- **Small enough for 75 minutes.**

Write it, read it back, and ask yourself: could someone who forgot everything start from this sentence alone? If not, rewrite it.

### 5. Prompt the checkpoint
Before they close, tell them to save a checkpoint so tonight's work is permanently safe:

Say: "Type 'commit this as a checkpoint' and I'll save a permanent snapshot you can always come back to."

If they ask why, one line: it means any future mistake can be undone back to this exact state. Also remind them `/rewind` exists for undoing changes inside a session.

If they don't want a checkpoint, don't push twice. Note in the log that there wasn't one.

### 6. Append the entry and close cleanly
Write the entry (format below), tell them the path, and end the session with the one line for tomorrow said out loud. That's the last thing they should read before closing the laptop.

## Output — save it
Append a dated entry to `~/build-log.md` (create the file if it doesn't exist). Never overwrite earlier entries — this log is the memory of the whole build.

```markdown
---

## <YYYY-MM-DD> — <project name>

**What changed**
- <plain-language line>
- <plain-language line>

**Working**
- <thing that was checked and behaves>

**Half-done**
- <thing> — <what's missing>

**Worth remembering**
- <decision or surprise, or omit this section>

**Checkpoint:** <saved / not saved>

**Tomorrow, first move:**
<One specific sentence.>
```

Tell them the path is `~/build-log.md` and give one next action: "Tomorrow, open this file first and read the last entry. Then do the first move and nothing else."

## Example (input → output)
**Input:** User spent 90 minutes on a landing page for a dog-walking business. They got the layout and copy in, the contact button half-wired, and never checked it on a phone.

**Output (appended to `~/build-log.md`):**
```markdown
---

## 2026-07-30 — paws-page

**What changed**
- The page now has a headline, a short "what I do" section, and three service cards with prices.
- Added a contact button under the cards.
- Swapped the fonts to the ones you picked.

**Working**
- The page loads and reads top to bottom on a laptop. Copy is real, not filler.
- The three prices show correctly.

**Half-done**
- The contact button looks right but doesn't open anything yet — it needs your email or phone number wired in.
- Never opened on a phone, so the layout on small screens is unknown.

**Worth remembering**
- You decided to lead with the neighborhood name in the headline. That's the thing that made it feel local, keep it.

**Checkpoint:** saved

**Tomorrow, first move:**
Wire the contact button to open a text message to your number, then open the page on your phone and tell me what looks wrong.
```

## Notes / edge cases
- The failure this prevents is the cold reopen. Without a one-line next move, the first 30 minutes of every session get spent re-reading instead of building.
- If the session was a mess and nothing works, log that honestly. "Nothing works, the page is blank, start by describing what you see" is a perfectly good next move.
- Never write a to-do list in the tomorrow line. One move. Extra ideas go in the half-done list or into the plan file.
- If they've been going for hours and things are getting worse, tell them to stop. The log will still be there. Tired building is where the mess comes from.
- If the project has no plan yet and it shows, point them at **plan-first** for the next session.
- On Sunday, this log is what **weekly-review** reads to see what actually shipped, so keep the entries honest.
