---
name: research-brief
description: Turns "I need to understand X before Monday" into a one-page brief you can actually use. The answer up front in three lines, then what's true, what's contested, what nobody agrees on, the numbers with dates attached, and what to read if you want more. Everything is sourced, and anything that couldn't be checked is marked unverified instead of guessed. Use when the user says "research this for me", "what do I need to know about", "brief me on", "I have a meeting about X", "catch me up on", "is X any good", "what's the deal with", "look into this", "I need to sound like I know this by Monday", or /research-brief.
---

# Research Brief — one page, sourced, by Monday

You need to walk into something knowing enough. Not a reading list, not twenty tabs — one page that says what's true, what's argued about, and what the numbers actually are. This skill goes and finds it, marks where every claim came from, and refuses to fill gaps with confident guesses.

## Setup
None. This skill works out of the box.

## Steps

### 1. Pin the question
Take what they gave you and write the question back in one sentence, sharper than they said it. Then ask **one** thing: **"What are you going to do with this?"** — a meeting, a decision, a purchase, a piece of writing, an interview.

That changes the brief completely. A brief for a purchase needs prices and failure modes. A brief for a meeting needs the two arguments and who holds them. Say which shape you're writing before you start.

If the question is too broad to answer in a page ("tell me about AI"), narrow it to one answerable version and say plainly what you narrowed it to.

### 2. Go and look
Use web search if it's available. If it isn't, say so in one line at the top of the brief and work from what you know — but mark every claim you can't source as `[unverified]` and don't pretend otherwise.

Search deliberately, not once:
- The plain question, as a person would type it.
- The question plus "criticism" or "problems" — the strongest case against is the part most briefs miss.
- The most specific number in the question, plus a year.
- The primary source, not the article about it. If a report, a filing, a paper, or an official page exists, go to that. Summaries of summaries drift.

Aim for five to ten sources across at least three different owners. Three articles all quoting the same press release is one source wearing three hats — say so if that's what you find.

### 3. Sort what you found into three piles
This is the structure that makes a brief useful, and it's the step people skip.

- **Settled** — multiple independent sources agree, and there's a primary source behind it. State it plainly.
- **Contested** — credible people disagree. Give both sides in one line each, and say who holds each position and what their interest is. Never average two positions into a fake middle.
- **Unknown** — nobody has good data, or the data is too new to trust. Saying "nobody knows this yet" is a genuine finding and often the most useful line on the page.

If everything lands in "settled", you probably searched too narrowly. Go back and search for the criticism.

### 4. Handle numbers carefully
Every number gets three things: **the figure, the date it's from, and where it came from.** A number without a date is not information.

- Copy figures exactly. Never round to make them tidier.
- If two sources give different numbers, show both and say why they differ (different years, different definitions, different methods).
- If a number is older than about 18 months in a fast-moving area, mark it `[may be stale]`.
- If you cannot find a number the user clearly needs, write `[not found]`. Never estimate one and never let a plausible figure through unsourced.

### 5. Write the answer up front
The first thing on the page is **three lines that answer the question.** Someone reading only those three lines should be able to hold a sensible conversation.

Then the rest of the brief backs them up. Don't build to the conclusion — lead with it.

### 6. Add the read-more and the honest gaps
Two to four sources with one line each on why that one is worth the time and roughly how long it takes. Best first. Never a wall of links.

Then a short **What I couldn't verify** section. List anything you looked for and couldn't confirm, anything that rested on a single source, and anything where the sources plainly conflict. This section is what makes the rest of the brief trustworthy — a brief with no gaps section is a brief that's hiding them.

## Output — save it
Write to `~/research/<topic-slug>-<YYYY-MM-DD>.md` (create `~/research/` if needed):

```
# <Question> — brief
*Written <date>. For: <what they're using it for>.*

## The answer (3 lines)
## What's actually true
## What's contested
## What nobody knows yet
## The numbers
## If you want more
## What I couldn't verify
## Sources
```

Under **Sources**, list every source with its title, who owns it, and the date. Tell the user the path, and paste the three-line answer into your reply so they get the point without opening the file.

## Example (input → output)
**Input:** "I've got a call Monday with someone selling us a four-day week trial. I know nothing. Brief me."

**Output (saved to `~/research/four-day-week-2026-07-30.md`), compressed:**

> **The answer:** Most published four-day-week trials report that productivity held steady and staff turnover dropped. The strongest evidence comes from self-selected companies that volunteered, which is the main reason critics don't accept the results. The open question isn't whether it works in a trial — it's whether it holds after two or three years, and almost nobody has data that long.
>
> **What's actually true:** Several multi-company pilots have run since 2022, with most participating companies choosing to continue afterwards. Reported sick days fell in the pilots that measured them.
>
> **What's contested:** Whether the gains come from the shorter week or from the meeting and process cleanup companies do to prepare for it. Advocates say it's the week; sceptics say you could get most of it without cutting a day. Both sides are reading the same trials.
>
> **What nobody knows yet:** How it holds up in shift work, hospitality, and healthcare, where output is tied to hours on site. The pilots skew heavily to office and software work.
>
> **The numbers:** Reported "would continue" rates from pilot companies have run high across several published trials — treat any single percentage you're quoted on the call as coming from one specific pilot, and ask which. `[figures vary by pilot; ask for the source of any number they give you]`
>
> **What I couldn't verify:** Long-run figures past three years — I couldn't find a published study that tracks companies that far. Anything you're told about long-term effects on Monday is likely extrapolation.
>
> **Ask on the call:** which pilot their numbers come from, what the sample was, and whether any of it covers a business shaped like yours.

## Notes / edge cases
- The beginner failure mode this prevents: reading five articles that all quote the same press release and coming away feeling informed. Count sources by who owns them, not by how many tabs are open.
- Never fill a gap with a plausible-sounding number. `[not found]` and `[unverified]` are correct answers. Getting caught with an invented figure in a meeting is worse than saying you don't know.
- If web search isn't available, say that in the first line of the brief and mark the whole thing accordingly. Don't quietly write from memory as though you'd checked.
- If the sources are all from people selling the thing, say so plainly — that's the finding.
- Fast-moving topics: put the date at the top of the brief and note that it goes stale. A brief without a date is a trap for the person who reads it in six months.
- If the brief exists to settle a choice, hand off to **decision-helper**. If they need to actually understand the mechanics rather than the landscape, hand off to **learn-anything**.
