---
name: weekly-review
description: A 20-minute Sunday reset that looks at what you actually shipped this week, why the stalled things stalled, and picks the ONE thing for next week — then makes you say what you're dropping. Writes a review file with your wins, your one thing, and three specific moves scheduled into the hours you actually have. Use when the user says "weekly review", "review my week", "what did I get done this week", "plan my week", "sunday reset", "I feel like I did nothing this week", "what should I focus on next week", "reset for the week", or types /weekly-review.
---

# Weekly Review — one Sunday hour that makes the next week count

Nightly progress is invisible. You build 90 minutes at a time, some nights go nowhere, and by Sunday it feels like you did nothing. That feeling is wrong most of the time, and it's the main reason people quit in month two. Progress is weekly, not nightly.

This is 20 minutes on a Sunday. You look at what actually shipped, name why the stalled things stalled, pick ONE thing for next week, and cut everything else. The cut is the point. Five priorities is zero priorities.

## Setup
None. This skill works out of the box.

## Steps

### 1. Pull the real evidence, don't rely on memory
People underestimate their own week badly. Go find the facts before asking them anything.

- Read `~/build-log.md` if it exists and pull every entry from the last seven days.
- Check `~/plans/` for any plan files and note what was in v1.
- If they name a project folder, check it for what changed this week (`git log --since="7 days ago" --oneline` if it's a git repo).

Then read it back to them as a list: "Here's what you actually did this week." If the log is empty, skip to asking them directly — but say plainly that next week they should run **session-wrapup** at the end of each session so this step has something to work with.

### 2. Name the wins — including the small ones
List what shipped or moved. Be generous but honest. A win counts if:
- Something exists now that didn't exist Monday, or
- Something got in front of a real person, or
- A decision got made that was blocking everything else.

Learning something does not count as a win on its own. Neither does watching, reading, or planning. Say that gently but say it — it's the difference between a builder and a student.

If a real thing went live or got sent to a human, call it out on its own line. That's the rep that matters.

### 3. Name what stalled, and why — specifically
For each thing that didn't move, get the actual reason. Push past "no time" — everyone says no time. Ask which of these it really was:

- **Too big** — it never got started because it didn't fit in a 90-minute block
- **Unclear** — they didn't know what the next move was, so they did nothing
- **Stuck** — they hit a wall and went in circles (that's **stuck-unstick**)
- **Avoided** — they knew what to do and didn't want to do it. Usually the one that touches other people: sending it, posting it, asking for money.
- **Actually no time** — a real life week happened

The reason determines the fix, so don't accept a vague one. Write the reason next to each stalled item.

### 4. Pick the ONE thing
Ask: "If next week only produced one result, which one would make the week worth it?"

Rules:
- One. Not a top three. If they give three, ask which one they'd keep if they lost the other two.
- It has to be finishable in a week of stolen hours.
- It should end with something existing or something being seen by another person. Not "work on the site" — "the site is live and three people have the link."

Write it as a result, not an activity.

### 5. Force the cut
This is the step that makes the review real. Ask straight out: "What are you dropping this week?"

Make them name at least two things — actual projects, ideas, or side quests that are getting no attention for the next seven days. Write them down under a heading called "Not this week." Nothing is cancelled, it's parked, and parking things is what makes the one thing possible.

If they refuse to drop anything, point at the stalled list from step 3 and say the quiet part: that list is what happens when nothing gets dropped.

### 6. Schedule three specific moves
Ask which nights they actually have this week, and how long. Then place three moves into those slots. Each move:

- Fits in one sitting
- Is described as an outcome ("the pricing section is written and on the page"), not a task ("work on pricing")
- Serves the one thing

Three moves, not seven. If a night gets missed, three still gets you there. Seven guarantees failure and the guilt that comes with it.

### 7. Say the honest sentence
End with one plain line about the week: what pattern you noticed. "You ship fast when the move is written down the night before, and stall on anything that involves sending it to someone." Say it once, don't lecture, and put it in the file. Over a few weeks these lines become the most useful part of the document.

## Output — save it
Write to `~/weekly-review.md`, appending a new dated section at the top (keep old weeks below — the history is the point). Create the file if it doesn't exist.

```markdown
# Weekly Review

## Week of <YYYY-MM-DD>

**Shipped this week**
- <win>
- <win>

**Stalled, and why**
- <thing> — <specific reason>

**The ONE thing next week**
<A result, in one sentence.>

**Not this week (parked)**
- <thing>
- <thing>

**Three moves**
1. <night> — <outcome>
2. <night> — <outcome>
3. <night> — <outcome>

**Pattern I noticed**
<One honest line.>
```

Tell them the path, and give one next action: "Put those three moves in your calendar now, tonight, while you're still sitting here."

## Example (input → output)
**Input:** User built for four nights, got a landing page mostly done, never sent it to anyone, and also started a newsletter and a second project idea.

**Output (saved to `~/weekly-review.md`):**
```markdown
# Weekly Review

## Week of 2026-07-27

**Shipped this week**
- The dog-walking page exists: headline, three services with prices, contact button.
- Fonts and colors decided and locked, so that argument is over.
- Wrote the pricing copy that had been stuck for two weeks.

**Stalled, and why**
- Sending the page to anyone — avoided. You've had a working link since Wednesday and haven't sent it.
- The newsletter — too big. There's no first issue written and no list to send it to.
- The second project idea — unclear. It's a sentence, not a plan.

**The ONE thing next week**
The page is live at a real link and five real people have opened it.

**Not this week (parked)**
- The newsletter
- The second project idea

**Three moves**
1. Tuesday — the page is live at a URL you can text to someone
2. Thursday — you've sent the link to five people and asked them one question: "what do I sell?"
3. Saturday — the page is fixed based on what those five people said

**Pattern I noticed**
You build fast and stop the moment the next step involves another human seeing it. The building isn't the bottleneck. Sending is.
```

## Notes / edge cases
- If the week genuinely produced nothing, don't manufacture wins. Say it plainly and make next week's one thing very small — one visible result in one sitting. A tiny finished thing rebuilds momentum faster than a pep talk.
- If they list five priorities, keep asking "which one would you keep" until there's one left. Don't compromise on this.
- Never invent numbers or results they didn't tell you. Read the log, ask if it's thin.
- If the same thing stalls three weeks running for the same reason, that's the real project. Say so.
- If most items stall because they're too big, next week starts with **plan-first**, not with building.
- If the build log is empty every week, the fix is upstream: get them running **session-wrapup** nightly before this review can do its job.
