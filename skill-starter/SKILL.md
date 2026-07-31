---
name: skill-starter
description: Turn a job you keep asking Claude to do into your own reusable skill, so you type one slash command instead of re-explaining every time. Interviews you for the job, the words you actually use to ask for it, the steps, and the file it should save — then writes a working SKILL.md into ~/.claude/skills/ and tells you how to test it. Use when the user says "make me a skill", "turn this into a skill", "I keep asking for the same thing", "how do I make my own slash command", "build a skill for this", "I do this every week, can Claude just do it", "custom skill", "skill starter", or types /skill-starter.
---

# Skill Starter — bottle the thing you keep asking for

You've asked Claude for the same kind of thing two or three times. You re-typed the same explanation, got a slightly different answer each time, and fixed it by hand. That's the signal. A skill freezes the good version so you get it the same way every time, from one slash command.

This is the skill that makes you a builder instead of a consumer. Everything else in this repo is someone else's job bottled up. This one bottles yours.

## Setup
None. This skill works out of the box.

## Steps

### 1. Check the trigger is real
Ask: "What's the job, and how many times have you asked Claude for it?"

- **Fewer than two times:** tell them to wait. You can't bottle a job you haven't done yet — you'd be guessing at the steps. Do it manually once more, then come back.
- **Two or more times:** good, keep going. Ask them to paste one of the actual prompts they used, or describe the last time they asked for it. Real past attempts are the best raw material.
- **It's a one-off:** say so plainly and just do the job instead of building a skill for it.

### 2. Nail the one job
Ask them to finish this sentence: "This skill takes ___ and gives me ___."

Push until both halves are concrete. "Takes my messy notes and gives me a clean weekly update email" is a skill. "Helps with my content" is not.

Then apply the One Job Rule out loud: if the answer has an "and" in the middle that hides a second job, split it. Two half-skills are worse than one that works. Tell them which half you're building now and note the other for later.

### 3. Get the trigger phrases — in their real words
This is the part people get wrong, so explain why it matters: the `description` field is the only thing Claude reads when deciding whether to fire the skill. If it's written in tidy language and the user types clumsy language, the skill sits there and never runs.

Ask: "If you needed this in six months and forgot the skill existed, what would you type?"

Collect five to eight phrasings. Push for the sloppy ones — the half-sentences, the typos-in-spirit, the way they'd say it at 11pm. "write my monday email", "that weekly update thing", "recap my week for the team". Include the slash form too.

### 4. Walk the steps
Ask them to talk you through how they'd do the job by hand, start to finish. Turn that into four to seven steps, each doing one thing.

For each step, capture the specifics that make the output good:
- The actual questions to ask them
- The actual format or template to fill
- The actual check that says "this is right"

If they can't describe a step, that's a step Claude has to decide on its own — write a clear rule for it rather than leaving it blank.

### 5. Decide what file it saves
Every skill should end with a real file at a real path. Ask: "Where should the result live so you can find it later?"

Pick a sensible path under `~/` — for example `~/emails/weekly-update.md` or `~/clients/<name>/brief.md`. Chat output disappears. A file doesn't.

### 6. Write the skill
Pick a short lowercase slug with dashes (this becomes their slash command). Create `~/.claude/skills/<slug>/` and write `SKILL.md` in this shape:

```markdown
---
name: <slug>
description: <what they get, then the trigger phrases in quotes, comma separated, including /<slug>>
---

# <Title> — <short tagline>

<2-3 sentences: the problem, and what lands at the end.>

## Steps

### 1. <Verb-first step>
<The actual questions, template, and checks.>

### 2. ...

## Output — save it
<Exact path. Exact contents. The one next action.>

## Notes
- <what to do when the input is thin>
- <the mistake this prevents>
```

Write it in their voice using their words. Then read the `description` back to them out loud and ask: "Would that fire if you typed your own clumsy version?" Add whatever's missing.

### 7. Test it
Tell them the exact sequence:

1. Start a new Claude Code session (skills load at startup — a skill written mid-session won't be live yet).
2. Type `/<slug>`.
3. If it runs, do one real job with it and fix whatever came out wrong.

If `/<slug>` doesn't appear, the folder name and the `name:` field don't match, or the file isn't at `~/.claude/skills/<slug>/SKILL.md`. Check both.

## Output — save it
Write `~/.claude/skills/<slug>/SKILL.md`. Print the full file back in the chat, state the exact path, and give one next action: "Restart Claude Code and type `/<slug>` to run it for real."

## Example (input → output)
**Input:** "Every Friday I ask Claude to turn my messy week notes into a short update for my three clients. I've done it about five times and it comes out different every time."

**Output (saved to `~/.claude/skills/client-update/SKILL.md`):**
```markdown
---
name: client-update
description: Turn your messy week notes into a short, calm client update email you can send as-is. Use when you say "write my client update", "friday update", "that weekly email thing", "recap the week for my clients", "update my clients", or /client-update.
---

# Client Update — Friday notes to sendable email

You end the week with scattered notes and no energy to write three emails. This turns the notes into one short update per client, in a shape they can read in 20 seconds.

## Steps

### 1. Get the notes
Ask for this week's notes, however messy. If they say "I didn't write any", ask three questions instead: what shipped, what's stuck, what's next.

### 2. Split by client
Sort every line under a client name. Anything that fits nobody goes in a leftover pile and gets dropped.

### 3. Write each update
Four lines per client, in this order: what got done, what's next, anything you need from them, one line of reassurance. No apologies. No filler.

### 4. Check the tone
Read each one back. If it sounds anxious or over-explains a delay, cut it to one calm sentence.

## Output — save it
Save all updates to ~/clients/updates/<date>-updates.md, one per client, separated by a line. Tell them the path and to paste each one straight into email.

## Notes
- Thin notes mean a short update, not an invented one. Never make up progress.
- If a client had zero activity, say that plainly and give a date for the next real update.
```

## Notes / edge cases
- Skills only load when a session starts. If theirs doesn't show up, that's almost always why — restart before debugging anything else.
- If the job changes every time, it isn't a skill yet. Do it manually until a shape repeats.
- Keep the first version small. A skill they actually run beats a perfect one they abandon halfway through writing.
- A skill can be edited any time. Tell them to fix the `SKILL.md` the moment output disappoints them, rather than working around it in chat.
- If the job is really "set rules for one project," that's **claude-md-builder**, not a skill.
- If they want to build the same skill for five different jobs, run this once and let them repeat it. Don't batch — each interview is where the quality comes from.
