---
name: stuck-unstick
description: Get out of the loop where Claude keeps giving you the wrong thing and you keep re-asking. Diagnoses which of the five common traps you're in — the ask is too big, you're describing the fix instead of what you saw, the chat is polluted, you changed three things at once, or you're trying to edit code yourself — then hands you the exact next sentence to send. Use when the user says "I'm stuck", "Claude keeps giving me the wrong thing", "we're going in circles", "it's not listening to me", "I've asked five times", "it broke and now it's worse", "this isn't working", "I keep having to redo this", "help I'm going round in circles", or types /stuck-unstick.
---

# Stuck / Unstick — a triage for going in circles

You asked for a change. It came back wrong. You asked again, it came back differently wrong. Now you're eight messages deep, the thing is worse than when you started, and you're starting to think you're bad at this. You're not. You're in one of five traps, and each has a specific way out.

This skill finds the trap and hands you the exact sentence to send next. It doesn't fix your project. It fixes the loop.

## Setup
None. This skill works out of the box.

## Steps

### 1. Take the temperature first
Before diagnosing anything, say one calming true thing: nothing is broken permanently. `/rewind` undoes changes in this session (Esc twice on an empty input box does the same). If a checkpoint was saved, everything can go back to that exact state. They cannot ruin the project from here.

Then ask two questions and wait:
1. "What did you ask for, in your own words?"
2. "What did you get instead?"

Take the answers at face value. Don't start solving yet.

### 2. Diagnose the trap
Match what they told you against these five. Name the trap out loud in plain words — beginners feel much better the moment the problem has a name.

**Trap 1 — the ask was too big.**
Signs: the request had "and" in it, or covered a whole page, or was a paragraph long. Each attempt fixes one part and breaks another.
*The move:* split it. Pick the single smallest piece and ask for only that.

**Trap 2 — describing the fix instead of the symptom.**
Signs: they're saying "change the padding", "make the div smaller", "use flexbox" — instructions about code rather than what they saw. They're guessing at a cause and Claude is dutifully implementing the wrong guess.
*The move:* describe what you SAW. Not what you think caused it. "On my phone the button is cut off on the right side" is a hundred times better than "fix the padding."

**Trap 3 — the chat is polluted.**
Signs: 40-plus messages, several abandoned directions, Claude referring back to something they gave up on an hour ago. The old wrong turns are still in the room.
*The move:* start a fresh session with a summary. Old context is dragging every answer sideways.

**Trap 4 — three things changed at once.**
Signs: they asked for several changes together, something broke, and nobody can tell which change did it.
*The move:* undo back to when it worked, then change one thing and look at it. Then the next. Slower feels slower and is actually faster.

**Trap 5 — trying to edit code by hand.**
Signs: they opened a file, changed something, and now it's worse or nothing loads. Or they're asking which line to edit.
*The move:* stop editing. Close the file. Describe the outcome you want in plain English and let Claude make the change. They are the director, not the typist.

If two traps fit, name both but pick the one to fix first — usually the biggest ask or the dirtiest context.

### 3. Hand back the exact next sentence
This is the deliverable. Don't explain the principle and leave them to write it — write the sentence for them, in their words, ready to send.

A good unstick sentence has four parts:
- **What you see now:** "The contact button is cut off on the right on my phone."
- **What you want instead:** "It should sit fully on screen with space around it."
- **The one thing to change:** "Only change that button. Don't touch anything else on the page."
- **How we'll know:** "Then show me the page so I can look at it again."

Give them one sentence to send, in a copy-ready block. If the trap is polluted context, the sentence is a fresh-session opener instead — see the next step.

### 4. If the fix is a fresh start, write the handoff
When trap 3 is the diagnosis, don't just say "start a new chat." Write the summary paragraph they'll paste into the new session so they don't lose the good parts. Include:

- What the project is, in one sentence
- What's working right now
- What's broken, described as what they see
- What was already tried and did not work, so it doesn't get tried again
- The one thing to do next

Then tell them: close this session, open a new one in the same folder, paste that paragraph.

### 5. Set the loop expectation
Say the thing nobody told them: five to ten rounds of "describe, look, react" is normal. That IS the workflow. Going back and forth is not evidence you're failing — it's evidence you're building. What's not normal is going back and forth without looking at the result between rounds. Look every time.

### 6. Give explicit permission to reset
End with this, plainly: if it's still going in circles after two more tries, use `/rewind` to put things back and start the piece over from the last good state. Restarting a 40-minute piece of work is cheap. Fighting a broken direction for three nights is not. Beginners think restarting means failing. It's the fastest move available to them.

## Output — save it
Write the diagnosis and the next sentence to `~/build-log.md` as a dated "stuck" entry (create the file if it doesn't exist), so the pattern is visible over time:

```markdown
---

## <YYYY-MM-DD> — stuck: <project name>

**What you asked for:** <their words>
**What you got:** <their words>
**Trap:** <trap name, one line on why>

**Send this next:**
<the exact sentence>

**If it's still stuck after two tries:** /rewind and restart this piece from the last good state.
```

Tell them the path, and give one next action: "Copy the sentence above and send it as your next message."

## Example (input → output)
**Input:** "I've asked four times to make the page look right on my phone and it keeps changing other stuff. Now the header is broken too and I don't know what happened."

**Output (saved to `~/build-log.md`):**
```markdown
---

## 2026-07-30 — stuck: paws-page

**What you asked for:** "make it look right on my phone"
**What you got:** phone layout still off, and now the header is broken too
**Trap:** The ask was too big. "Look right on my phone" covers the whole page, so every attempt moves several things and breaks something new.

**Send this next:**
On my phone, the three service cards are squashed side by side and the text is too small to read. I want them stacked one above the other, full width, with readable text. Change only the cards — leave the header and the button alone. Then show me the page so I can look.

**If it's still stuck after two tries:** /rewind and restart this piece from the last good state.
```

## Notes / edge cases
- If they can't say what they saw, ask them to read the screen out loud to you. "It's broken" is not a symptom; "the page is blank and white" is.
- If they've been at it more than an hour and are frustrated, say to stop for the night and run **session-wrapup**. Tired debugging makes more mess.
- If the same trap shows up three times across sessions, the real fix is upstream: a rule in **claude-md-builder**, or a smaller scope from **plan-first**.
- Never tell them to open a file and change a line. That's trap 5 and it makes things worse.
- If the project genuinely has no last-good state to rewind to, say so and rebuild the broken piece from a plain description. Don't pretend a checkpoint exists.
