---
name: safety-net
description: Sets up your two undo systems so you can experiment without worrying you'll wreck your project — /rewind for instant undo and Git checkpoints for permanent saves. Walks you through making your first checkpoint on the project you have open, then saves a one-page cheat sheet with the exact recovery moves for "I broke it", "go back one step", and "go back to this morning". Use when the user says "I'm scared I'll break something", "how do I undo", "can I go back", "I broke my project", "how do I save my work", "what's a checkpoint", "how does rewind work", "is there an undo", "I want to try something risky", or "/safety-net".
---

# Safety Net — two undos, so you can experiment

Beginners build timidly because they think one bad prompt ruins everything. It doesn't. You have two separate undo systems, and once they're set up you can try things you'd otherwise avoid. This skill explains both, makes your first real checkpoint on your actual project, and leaves a cheat sheet you keep open.

## Setup
None. This skill works out of the box.

## Steps

### 1. Say the thing they need to hear
Open with it, plainly: "You can't really break anything. There are two undo buttons, and by the end of this you'll have both working on this project."

Then name the two, and name the difference — this is the part everyone gets muddled:

- **`/rewind`** — automatic, instant, short-term. Claude Code takes a snapshot before every change it makes. You didn't set this up and you don't have to. It's for "the last thing you did made it worse."
- **Git checkpoints** — manual, permanent, long-term. You say "commit this as a checkpoint" and that exact state of the project is saved forever with a name. It's for "get me back to how it was on Tuesday when it worked."

One line to lock it: **rewind undoes moves, checkpoints save days.**

### 2. Teach /rewind properly
Cover exactly this, no more:
- Type `/rewind` in Claude Code. You get a list of recent checkpoints.
- Faster: press **Esc twice** with an empty input box. Same thing.
- Pick the point from before things went wrong. Your files go back to that state.
- It's automatic — it happens before every change whether you ask or not.
- What it doesn't do: it's for recent work in this session, not for going back days. That's what checkpoints are for.

Then have them actually try it once. Say: "Ask Claude to make one small pointless change — change a heading to the word BANANA. Look at it. Then type `/rewind` and put it back." Doing it once removes the fear permanently. Reading about it does not.

### 3. Check whether Git is on this project
Ask which project they're working on and get the folder path. Check whether it's already a Git repo — look for a `.git` folder in it.

Don't explain Git as a version control system. Explain it as: "a way to save a permanent snapshot of the whole project with a name, so you can always come back to it."

If it isn't set up, you do it for them. They say the word, you run it. Never hand a beginner a list of Git commands to type.

### 4. Make their first checkpoint right now
This is the part that has to actually happen, not just get described.

Have them say to Claude: **"Commit this as a checkpoint called 'working version before I start experimenting'."**

You do the rest. Then confirm out loud what just happened: "That state of your project is now saved permanently. Whatever you do next, you can get back to exactly this."

That sentence is the whole point of the skill.

### 5. Set the checkpoint habit
Give them the three moments to make one. Three, not ten:
- **When something works.** The moment the page loads right or the feature does the thing. Before you touch it again.
- **Before something risky.** A big redesign, a new feature, anything you're unsure about.
- **At the end of every session.** Part of closing the laptop — the last 10 minutes of a 90-minute night are checkpoint plus tomorrow's one-line next step.

Tell them how to name checkpoints: say what state the project is in, not what you did. "homepage working on mobile" beats "changes."

### 6. Write the three recovery moves
These are the three situations they'll actually be in. Write them as scripts they read aloud.

**"I broke it and I don't know how."**
Don't debug. Type `/rewind`, or press Esc twice. Pick the point before it broke. Then re-ask for what you wanted in a smaller step.

**"Go back one step."**
Type `/rewind`, pick the most recent checkpoint. Or say to Claude: "Undo the last change you made."

**"Go back to this morning / to when it worked."**
Say to Claude: "Show me my checkpoints from today." Pick the one by name. Then: "Take the project back to the checkpoint called ___." Rewind won't reach that far — this is what checkpoints are for.

Add the escape hatch: **"I want the old version back but I also want to keep what I made since."** Say to Claude: "Save what I have now as a checkpoint, then take me back to ___." Nothing gets lost.

## Output — save it
Write to `~/claude-safety-net.md`. One page, no longer — this is a cheat sheet, not a manual.

It contains: the one-line difference between the two systems, the `/rewind` moves including Esc-Esc, the exact sentence for making a checkpoint, the three moments to checkpoint, the three recovery scripts word for word, the keep-both escape hatch, and the name and date of the first checkpoint they just made.

Tell them the path, then the one action: keep this file open in a tab while you build. Also tell them the true thing — now that both undos are working, the correct move is to go try something they were previously too nervous to try.

## Example (input → output)

**Input:** "I'm working on my portfolio site and I want to try a completely different layout but I'm scared I'll lose the version that works."

**Output (saved to `~/claude-safety-net.md`):**
```
YOUR TWO UNDOS
Rewind undoes moves. Checkpoints save days.

REWIND — instant, automatic
Type /rewind, or press Esc twice on an empty input box.
Pick the point from before it went wrong. Files go back.
For recent work only, not for going back days.

CHECKPOINT — permanent, you ask for it
Say: "Commit this as a checkpoint called '<what state it's in>'."
Make one when something works, before anything risky, and at the
end of every session.

YOUR FIRST CHECKPOINT
"portfolio working before layout experiment" — saved 2026-07-30.
You can always get back to exactly this.

IF I BROKE IT
Don't debug. /rewind, pick the point before it broke, re-ask smaller.

GO BACK ONE STEP
/rewind and pick the most recent. Or: "Undo the last change you made."

GO BACK TO WHEN IT WORKED
"Show me my checkpoints from today."
"Take the project back to the checkpoint called ___."

KEEP BOTH VERSIONS
"Save what I have now as a checkpoint, then take me back to ___."
```

Next action: go try the new layout. The old one is saved.

## Notes / edge cases
- The failure this prevents is timid building — beginners avoiding the interesting version because they're guarding the working one. The whole point of the checkpoint is permission to experiment.
- Make them actually do the rewind test in Step 2 and actually make the checkpoint in Step 4. A skill that only describes safety nets doesn't create the feeling of having one.
- Never hand them raw Git commands. They say the sentence, Claude runs it. If they want to learn Git properly later, that's a different day.
- If the project isn't a Git repo yet, set it up without making a thing of it. It's one step, it costs nothing, and it takes 10 seconds.
- If they've already broken something right now, do Step 6 first and set up the rest after. Fix the fire, then install the alarm.
- If they're staring at an error and don't know whether to rewind, hand off to **error-decoder** — it sorts errors into ignore, fix, or rewind.
