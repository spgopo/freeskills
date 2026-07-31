---
name: claude-orientation
description: Tells you exactly what to build first with Claude Code, and gives you tonight's one next move instead of a pile of ideas. Figures out where you are on the 9-stage beginner arc, picks ONE build, and saves a 30-day roadmap you can reopen every night. Use when the user says "I just installed Claude Code", "now what", "what should I build first", "where do I start", "I don't know what to do with this", "I have too many ideas", "what's my first project", "help me get started", "/claude-orientation", or when someone is clearly bouncing between projects and finishing none.
---

# Claude Orientation — one build, one next move

Most people install Claude Code, watch three videos, start five projects, and finish zero. That's not a discipline problem. It's a sequencing problem — nobody told them what order to do things in. This skill finds where you actually are, picks the single next build, and writes tonight's one-line move to a file you reopen every session.

## Setup
None. This skill works out of the box.

## Steps

### 1. Locate them on the arc
There is a 9-stage beginner arc. Each stage assumes the one before it. Read them out plainly, then ask which one they last finished:

1. **Install** — Claude Code is open and you've talked to it once.
2. **Memory** — you have a `CLAUDE.md` so Claude remembers who you are between sessions.
3. **Website** — one live page about you, on the internet, with a URL.
4. **Landing page** — a page with one clear action a visitor can take.
5. **Skills** — you've made one custom skill that does a repeat task for you.
6. **Game** — one small interactive thing, to prove you can build state and logic.
7. **Agents** — something that runs a job for you without you watching every step.
8. **Content** — you turn what you build into posts, so building compounds.
9. **Distribution** — you put the thing in front of real people on purpose.

Ask exactly two questions:
- "Which of these nine have you actually finished — not watched, finished?"
- "What have you tried to build so far, even if it went nowhere?"

If they can't answer the first, assume Stage 1.

### 2. Set the stage, and refuse to skip
Their stage is **the first one they have NOT finished.** Say it plainly: "You're at Stage N."

If they want to jump ahead — an agent at Stage 2, an app at Stage 3 — do not argue about ambition. Say what the skipped stage buys them in one line ("without a CLAUDE.md you re-explain yourself every night") and put the big idea in a Later list in the roadmap so it isn't lost. They keep the ambition, they just don't start there.

### 3. Kill the extra ideas
Ask: "List every project you're currently thinking about." Take the list and cut it to one.

Pick the survivor by these tests, in order:
- **Stage fit** — does it match the stage from Step 2?
- **Finishable in a week** — can it be done in five 90-minute nights? If not, cut its scope until it can.
- **Real audience** — is there one specific person they could send it to when it's done? Name that person.
- **Their own itch** — do they actually want it to exist?

Everything that loses goes in a **Parking Lot** section. Nothing gets deleted. That's the trade that makes people accept the cut.

State the winner in one sentence: "You are building ___ , for ___ , done when ___ ."

### 4. Cut it to a first version that ships this week
Beginners scope like a company. Shrink it. Apply the **One Job Rule**: the build does one thing. One page, one action, one outcome. If it has two features, remove one and put it in the Parking Lot.

Write a Done-When line that is checkable by looking, not by feeling: "a stranger can open this link on their phone and book a call" beats "the site is finished."

Remind them: **ugly-but-live beats pretty-but-local.** The first version being plain is correct.

### 5. Break the week into five nights
They work in stolen hours, roughly 90 minutes. Write five nights, each with ONE specific move. Each night follows the same shape: 5 minutes reopen and read the last note, 75 minutes on the one move, 10 minutes save a checkpoint and write tomorrow's line.

Nights should escalate: get something on screen, make it real, make it good, put it live, send it to one human. Night 5 is always "send it to a real person" — shipping to someone is the rep.

### 6. Write tonight's single next move
One line, one sentence, starts with a verb, doable in 90 minutes, and specific enough that they don't have to think when they sit down. Not "work on the site." More like: "Ask Claude to build a one-page site about me with my name, one sentence on what I do, and a button that opens my email."

Include the exact first thing they paste into Claude. Give them the words.

### 7. Sketch the 30-day arc
Four weeks, one line each, moving them forward through the stages. Keep it loose — this is direction, not a contract. Week 1 is the build from Step 3. Weeks 2-4 are the next stages in order.

## Output — save it
Write everything to `~/claude-roadmap.md`. Overwrite it if it already exists, but first read it and carry over anything from the old Parking Lot.

The file contains, in this order:
- **Where you are** — the stage number and name, one line on why.
- **The one build** — the sentence from Step 3, plus the Done-When line.
- **Tonight's next move** — one sentence, plus the exact text to paste into Claude.
- **This week, five nights** — five one-line moves.
- **The 30-day arc** — four lines, one per week.
- **Parking Lot** — every idea that got cut, so nothing feels lost.

Tell them the path. Tell them one thing: "Open this file at the start of every session. Do the next move. Then rewrite the next-move line before you close the laptop."

## Example (input → output)

**Input:** "I installed Claude Code last week. I want to build an app for my coaching business, a newsletter site, a Chrome extension, and maybe an AI agent that books calls. I haven't finished anything."

**Output (saved to `~/claude-roadmap.md`):**
```
WHERE YOU ARE
Stage 2 — Memory. Claude Code is installed but you have no CLAUDE.md, so
every session starts from zero.

THE ONE BUILD
You are building a one-page site about your coaching, for one client who
keeps asking "where can I read about what you do", done when that client
can open the link on their phone and see your offer and a way to contact you.

TONIGHT'S NEXT MOVE
Set up your CLAUDE.md so Claude knows who you are, then start the page.
Paste this: "Create a CLAUDE.md in my home folder with my name, what I do,
who I help, and how I like you to talk to me. Ask me the questions you need."

THIS WEEK
Night 1 — CLAUDE.md, then get any version of the page on screen.
Night 2 — Real words. Your offer in plain English, no placeholder text.
Night 3 — Make it look like you. One accent color, two fonts.
Night 4 — Put it live and get a URL.
Night 5 — Text the URL to that one client. Ask what's confusing.

30-DAY ARC
Week 1 — Live one-page site.
Week 2 — Turn it into a landing page with one clear action.
Week 3 — Build your first custom skill for a task you repeat.
Week 4 — Post what you built. Start Stage 8.

PARKING LOT
Coaching app. Newsletter site. Chrome extension. Call-booking agent.
All still yours. None of them are tonight.
```

## Notes / edge cases
- The failure this prevents is shiny-object syndrome. If they push back on cutting to one build, don't debate — point at the Parking Lot and move on. The list is the concession.
- If they've genuinely finished several stages, don't drop them at Stage 1 to be safe. Ask what they shipped and where it lives. Evidence sets the stage, not confidence.
- If they say "I don't have any ideas," don't brainstorm ten. Ask what they do all day and what part of it is annoying. The first build comes out of that in two questions.
- If input is thin — a one-line "now what?" — assume Stage 2, pick the one-page site, and write the roadmap anyway. A default plan beats an interview they'll abandon.
- Once they have the build picked and want the prompt to actually run it, hand off to **brief-builder**. If they get scared of breaking something, hand off to **safety-net** before they start.
