---
name: decision-helper
description: You're stuck between options and going round in circles. This forces a decision, not another summary — it gets the real options on the table, names what you're actually optimizing for, drags out the constraint you haven't said out loud, and gives you one clear recommendation with the reason in a single line, plus the first move to make today. Use when the user says "help me decide", "I'm stuck between", "I can't choose", "should I do X or Y", "I keep going back and forth", "what would you do", "I've been thinking about this for weeks", "talk me through this decision", "pros and cons", or /decision-helper.
---

# Decision Helper — pick one, move today

Being stuck is rarely a lack of information. It's usually an unnamed constraint, or two things you want that can't both win. This skill gets the real options out, names the trade you're actually making, and ends with one recommendation and one first move. Not a balanced summary — a call.

## Setup
None. This skill works out of the box.

## Steps

### 1. Get the options on the table — the real ones
Ask the user to state the decision in one sentence, then list every option they're weighing.

Then do the two things they won't do for themselves:
- **Add the missing options.** Almost every stuck decision is framed as two choices when there are four. The usual missing ones: do nothing for now, do a smaller version of one option, do both in sequence, ask someone for something that changes the choice entirely.
- **Cut the fake options.** Anything they've already ruled out but keep listing to feel thorough. Say plainly: "You're not going to do this one — dropping it."

End with a clean numbered list of the live options. Usually two to four.

### 2. Name what you're actually optimizing for
Ask: **"If only one of these could be true a year from now, which one?"** Give them the list to pick from — money, time, risk, learning, freedom, reputation, keeping the relationship, getting it over with, protecting your energy.

Make them pick **one**. Two is fine if they're genuinely tied, but no more. If they refuse to pick, that refusal is the actual problem and you should say so.

Then say back to them, in one line: "So you're optimizing for X, and you're willing to give up Y to get it." Watch whether they flinch. A flinch means you've got the wrong one.

### 3. Surface the constraint they haven't said out loud
This is the important step. People stay stuck because the real reason is embarrassing, or they haven't admitted it to themselves. Probe gently with the ones that fit:

- Is there a money number that decides this on its own? What's the smallest amount that would make it obvious?
- Is there a person whose reaction you're managing — a partner, a boss, a parent, a friend?
- Is there a date you're not counting from? A lease ending, a contract, a due date, a savings runway?
- Is one of these options actually about proving something to someone?
- Would you still be stuck if nobody ever found out which one you picked?
- What's the thing you'd be relieved about if the decision were made for you tomorrow?

The last question is the strongest one. Relief points at the answer. When something surfaces, write it down in one plain sentence — this is usually the whole decision.

### 4. Run the reversibility check
Ask: **if this turns out to be wrong, how hard is it to undo?**

- **Easy to undo** (you could reverse it in a week for under a few hundred and nobody gets hurt): decide now, on the spot. Say it directly: "This is cheap to reverse. You've spent more time deciding than fixing it would cost. Pick and go." Do not run a deep analysis on a reversible choice.
- **Hard to undo** (money you can't get back, a contract, a public move, a relationship, a house, quitting something): slow down for exactly **one specific reason** — name the single thing that would change the answer, and the single check that would settle it. One check, with a date on it. Not "do more research."

Never let a hard-to-undo decision drift into "think about it more." Give it a check and a deadline.

### 5. Make the call
Give one recommendation. Not a lean, not "it depends," not a table.

Format it exactly like this:

> **Do this:** <the option, in plain words>
> **Because:** <one line — the single reason it beats the others, tied to what they said they're optimizing for>
> **You're giving up:** <the real cost, stated honestly>
> **You'd be wrong if:** <the one condition that would flip this>

That last line matters. It tells them what to watch for, and it keeps you honest — if you can't name the condition, you don't have a recommendation, you have a preference.

### 6. Name the first move, today
One action, doable today, under 30 minutes. A message sent, a number looked up, a call booked, a form started, a line written. Not "start planning."

Then give the **decide-by date** for anything still open, and one line on what they'll know by then that they don't know now.

## Output — save it
Write to `~/decisions/<short-slug>-<YYYY-MM-DD>.md` (create `~/decisions/` if needed) with these sections:

```
# Decision — <one line>
## Options on the table
## What I'm optimizing for
## The constraint I hadn't said out loud
## Reversibility
## The call
## First move (today)
## Decide-by date
```

Tell the user the path. Then say the first move out loud in your reply, so they can do it without opening the file.

## Example (input → output)
**Input:** "I've been going back and forth for six weeks on whether to quit my job to go full time on my side thing. I make about £900 a month from it. I can't decide."

**Output (saved to `~/decisions/quit-job-2026-07-30.md`), compressed:**

> **Options:** (1) Quit now. (2) Stay and keep building nights. (3) Drop to four days and buy one build day a week. (4) Set a revenue number that triggers the quit.
> *You listed two. Options 3 and 4 are the ones you hadn't put on the table.*
>
> **Optimizing for:** risk — specifically not running out of money. You'll give up speed to get it.
>
> **The constraint you hadn't said:** your partner hasn't agreed to this. Every version of the plan you described assumes a conversation that hasn't happened.
>
> **Reversibility:** hard to undo. Quitting and re-hiring into the same salary is not a week's work. So: one check, not five — does £900/month grow when you add ten hours a week, or is it flat because of something other than time?
>
> **The call:**
> - **Do this:** ask for four days a week, starting next month.
> - **Because:** it buys the one thing you don't have — a real test of whether more hours moves the number — without betting the rent on it.
> - **You're giving up:** 20% of your salary, and the clean story of "I went all in."
> - **You'd be wrong if:** your employer says no to four days, in which case the decision becomes quit-or-stay and you'll need the revenue trigger instead.
>
> **First move today:** send your partner one message — "can we talk Thursday about me going to four days?" Twelve words. That's the blocker, not the spreadsheet.
>
> **Decide-by:** 30 September.

## Notes / edge cases
- The beginner failure mode this prevents: researching a reversible decision for six weeks. If it's cheap to undo, the answer is "pick one now" — say that and mean it.
- If the input is thin ("should I do this?"), get the options and the optimize-for before anything else. You cannot recommend without knowing what winning looks like to them.
- Never hedge at step 5. If you genuinely can't call it, say the two options are equivalent and tell them to pick the one they'd be relieved about — but say that as the recommendation, not as a shrug.
- If the decision turns on money, health, law, or immigration, still make the call on the parts you can, and flag the specific piece worth taking to a professional.
- If the choice hinges on facts nobody in the room has, hand off to **research-brief** for the one specific question, then come back and decide.
- If it hinges on a document they haven't properly read, run **doc-digest** on it first.
