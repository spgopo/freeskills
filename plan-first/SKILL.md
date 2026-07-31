---
name: plan-first
description: Turn a big fuzzy idea into a small written plan you approve before Claude touches a single file, so you ship a v1 instead of stalling on version five. Forces a hard scope cut, a "not in v1" list, the order of moves, and a plain-English definition of done — saved as a plan file you can reopen any night. Use when the user says "I want to build X", "help me plan this", "I have an idea", "plan this out first", "scope this down", "this is getting too big", "how do I break this up", "plan first", or types /plan-first. If they haven't picked a project at all yet, that's **claude-orientation**, not this skill.
---

# Plan First — decide what you're building before anything gets built

The number one thing that kills a beginner build isn't a bug. It's building too big. You describe the whole dream, Claude starts building the whole dream, and four nights later you have half of everything and none of it works. This skill takes the dream, cuts it to a v1 you can finish in a few sessions, and writes the plan down so you approve it before any file gets touched.

Nothing gets built in this skill. The output is a plan you agreed to, with a first move small enough to start tonight.

## Setup
None. This skill works out of the box.

## Steps

### 1. Get the idea out, whole
Let them ramble. Ask: "What are you trying to build, and who's it for?" Don't correct or shrink anything yet — you need the full picture before you can cut it.

Then read it back in three lines: what it is, who it's for, what it does. Make them confirm you understood before you go further. Half of all bad builds are a misunderstanding that never got caught in the first five minutes.

### 2. Find the one job
Ask: "If this only did ONE thing, and did it well, what would that thing be?"

Push until you have a single sentence with a single verb. "Lets a visitor book a call with me." "Shows my five best photos and my email." "Tells me what to eat this week."

This sentence is the spine. Every later question gets settled by asking whether it serves this sentence. Write it down word for word.

### 3. Cut hard — the v1 list and the later list
This is the whole point of the skill, so do it out loud and don't be gentle.

Take everything they described and sort it into two lists:

- **v1** — only what the one job needs to work for one real person. Aim for three to five items. If it's more than five, cut again.
- **Later** — everything else. Logins, accounts, payments, dashboards, admin panels, second pages, email lists, dark mode, animations.

For each thing you're cutting, say why in one clause: "Cut accounts — nobody can log in to something that doesn't work yet."

Then give them the reassurance that makes the cut stick: nothing on the later list is lost. It's written down. They can add it in week two, once the thing exists and someone has actually used it.

If they push back on a cut, ask one question: "Does the one job work without it?" If yes, it goes to Later.

### 4. Order the moves
Turn v1 into three to six moves, in order, each small enough to finish in one 90-minute sitting.

Rules for the order:
- The first move must produce something they can look at. Not setup, not structure — something visible on screen.
- Each move builds on the one before it, so nothing sits half-finished.
- Name each move as an outcome, not a task: "the page shows my offer and a button" beats "build the layout."

### 5. Write down what "done" looks like
Ask: "How will you know v1 is finished?" Then turn the answer into a checkable list of three to five lines a normal person could tick off by looking at the screen.

Good: "A stranger on a phone can read what I do and tap one button to message me."
Bad: "It works well."

If they can't tell whether it's done by looking at it, it isn't a definition of done — rewrite it until it is.

### 6. Point at plan mode
Tell them the habit this skill is training. Before any real build session, they can put Claude in plan mode — Claude thinks the change through and shows the plan without touching files, and they approve it before anything happens. Same idea as this skill, at the level of a single session.

Say it plainly: reading a plan for two minutes is cheaper than undoing an hour of the wrong build.

Also remind them they can't really break anything. `/rewind` undoes changes. "Commit this as a checkpoint" makes a permanent save they can always come back to.

## Output — save it
Write the plan to `~/plans/<project-slug>-plan.md` (create `~/plans/` if needed), in this shape:

```markdown
# <Project> — v1 plan
Written: <date>

## The one job
<Single sentence.>

## In v1
- <item>
- <item>
- <item>

## NOT in v1 (later list)
- <item> — <one clause on why it waits>
- <item> — <one clause on why it waits>

## The moves, in order
1. <outcome-shaped move>
2. <outcome-shaped move>
3. <outcome-shaped move>

## Done when
- [ ] <checkable line>
- [ ] <checkable line>
- [ ] <checkable line>

## First move — start here
<One sentence. The exact thing to do in the next session.>
```

Tell them the path, and give one next action: "Open a new session, read the first move, and do only that."

## Example (input → output)
**Input:** "I want to build a site for my meal-prep thing. People pick their meals, pay, get a weekly plan emailed to them, I want a login so they can see past orders, and maybe a recipe blog."

**Output (saved to `~/plans/meal-prep-plan.md`):**
```markdown
# Meal Prep Site — v1 plan
Written: 2026-07-30

## The one job
A local person reads what I offer and messages me to order a week of meals.

## In v1
- One page that says what the meals are and who they're for
- This week's three meal options with a photo and a price
- One button that opens a message to me
- Works on a phone

## NOT in v1 (later list)
- Logins and past orders — nobody can log in to something nobody has bought from yet
- Online payment — take the first five orders by message and get paid however you already get paid
- Recipe blog — that's a second project wearing this one's clothes
- Automatic weekly emails — write the first four by hand and see if anyone reads them

## The moves, in order
1. The page exists and says the offer clearly, top to bottom
2. The three meals show with photos and prices
3. The message button works from a phone
4. A friend opens it on their phone and can tell me what I sell in one sentence

## Done when
- [ ] I can open the link on my phone and read the whole thing without pinching
- [ ] A stranger can tell me what I sell after ten seconds
- [ ] Tapping the button opens a message to me with something already typed
- [ ] The link is live and I've sent it to one real person

## First move — start here
Build one page that says what the meals are, who they're for, and nothing else. No photos yet.
```

## Notes / edge cases
- If they resist every cut, ask for the deadline. A real date makes the cut for you.
- If the idea is genuinely two projects, say so and make them pick one. Don't plan both.
- Thin input ("I want a website") means you ask what it's for and who sees it. Never plan a site with no visitor in mind.
- If they already started building and it's a mess, this skill still works — plan the v1 from where they are and treat the mess as the later list.
- When the plan is approved and they're ready to build, they leave this skill. Come back at the end of the session with **session-wrapup** so tomorrow starts in five minutes instead of thirty.
- Revisit the plan whenever the build stops making sense. A plan you never reopen is a plan you didn't need.
