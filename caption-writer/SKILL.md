---
name: caption-writer
description: Get a ready-to-post caption about something you built, made, or learned — written in your voice, in the right length for Instagram, LinkedIn, X, or TikTok. Picks one of four post shapes that actually work and writes a first line that stops the scroll. Use when the user says "write a caption", "caption for this post", "I built something, what do I say", "how do I post about this", "write the copy for my Instagram post", "I don't know how to talk about what I made", "help me post this without sounding salesy", or "/caption-writer".
---

# Caption Writer — post about the thing you made without sounding like an ad

Most people build something and then go quiet, because writing about it feels like bragging. The fix is to stop announcing yourself and start showing the thing. This skill picks the right post shape, writes a first line that does all the work, and saves a finished caption you can paste and post.

## Personalization
This skill works in *your* brand voice. Before running, load the brand profile at `~/.claude/brand-profile.md`.
- If it doesn't exist, run the **personalize** skill first (or just tell me your name, niche, offer, and audience — I'll create it).
- If a field this skill needs is blank, I'll ask one or two quick questions and save the answers back to the profile so you only answer once.
- Never invent facts or results about the user — use only what's in the profile, or ask.

## Steps

### 1. Get the raw material
Ask for whatever they have, in plain words. Two questions, max:
- "What's the thing? Tell me what it is and what it does, like you're texting a friend."
- "Is there a link, a screenshot, or a video? And which platform is this going on?"

If they ramble, that's good — the best lines are usually already in their rambling. Pull exact phrases they used and keep them. Do not clean up their words into marketing language.

If they only have a vague "I've been working on stuff," ask one more: "What changed today that didn't exist yesterday?" That answer is the post.

### 2. Pick the post shape
Choose ONE of four. Say which you picked and why, in one line. Never blend two.

- **Show the thing.** Best when there's a screenshot, video, or live link. The caption's job is small: say what it is, who it's for, and one honest detail about making it. The visual carries the post.
- **The lesson from a mistake.** Best when something broke, took five tries, or they were wrong about something. Highest trust of the four. Structure: what I believed → what actually happened → what I'd do now.
- **Before and after.** Best when there's a visible or measurable change: old page vs new page, 3 hours vs 10 minutes, empty list vs 40 people. Needs a real contrast, not a vibe.
- **Honest progress update.** Best when nothing is finished. This is the build-in-public post. Structure: where it is right now → the one hard part → what's next. Unfinished is allowed. Fake finished is not.

### 3. Write the first line
The first line is the whole post. On every platform, it's the only line most people see before deciding.

Rules:
- No throat-clearing. Banned openers: "Excited to share", "I'm thrilled to announce", "So I've been thinking", "Hey everyone", "Quick post about".
- Start at the sharpest moment. Drop the wind-up sentence and open on the second sentence you would have written.
- Be specific and concrete. "I built a tool that tells you if your rent is too high" beats "I built something I'm proud of."
- A number, a strange detail, or an admission all work. Cleverness usually doesn't.

Write three candidate first lines. Show them to the user, pick the strongest yourself, and say why in one line. They can override.

### 4. Write the body for the platform
One idea per line. Blank line between lines. No paragraph blocks.

Match the platform:
- **Instagram** — 4 to 8 short lines. The first line has to work before the "more" cut. Conversational. Up to 5 hashtags at the very bottom, plain and specific, no hashtag soup.
- **LinkedIn** — 6 to 12 short lines. Same voice, slightly more context about who it helps and why it matters. No corporate register, no "humbled to". First 2 lines show before the "see more" cut.
- **X** — under 280 characters, or a single tight post. Cut every word that isn't load-bearing. No hashtags.
- **TikTok** — 1 to 2 lines only. The caption supports the video, it doesn't repeat it. Add a question that invites comments.

### 5. Add the CTA
If a link is involved, do NOT put a raw link in the post on Instagram or TikTok — it kills reach and nobody can tap it anyway. Use a comment keyword instead:

> Comment GAME and I'll send you the link.

Pick a keyword that's one word, all caps, and related to the thing (GAME, TOOL, SITE, BUDGET, TRACKER). Comments turn into conversations, and conversations are where people actually buy. On LinkedIn and X a link in the post is fine, but a keyword still gets more replies.

If there is no link, end with a real question they'd actually answer — about the thing, not "what do you think?" Something like "What would you want it to do next?"

One CTA per post. Never two.

### 6. Read it back out loud
Before saving, run this check on the draft:
- Does the first line make someone stop, with no context?
- Is there any line that only exists to sound impressive? Cut it.
- Would they say this sentence to a friend at a table? If no, rewrite it.
- Any of these words? unlock, leverage, elevate, game-changer, journey, thrilled, humbled. Cut them.
- Is there exactly one ask?

## Output — save it
Write the finished caption to `~/captions/YYYY-MM-DD-<short-slug>.md` (create `~/captions/` if needed).

The file contains: the platform, the post shape chosen, the final caption exactly as it should be pasted (in a copy-ready block), the two runner-up first lines, and the comment keyword if there is one.

Tell the user the path. Then tell them the single next action: post it, and reply to every comment within the first hour.

## Example (input → output)
**Input:** "I made a little browser game where you dodge falling emails. It's dumb but it works and it's live. Posting on Instagram."

**Output (saved to `~/captions/2026-07-30-email-dodge-game.md`):**

Shape: Show the thing.

> I made a game where you dodge falling emails and it is genuinely stressful.
>
> It started as a joke about my inbox.
>
> Took four nights. Most of that was making the emails fall at a speed that felt mean but fair.
>
> It runs in your browser. No download, no signup.
>
> Comment GAME and I'll send you the link.

Runner-up first lines: "My inbox became a video game." / "Four nights of work to make falling emails feel mean but fair."

## Notes / edge cases
- The failure mode this prevents: writing a caption that describes how the person feels instead of showing what they made. Feelings don't travel. The thing does.
- If they have nothing built and nothing learned, don't write a post. Tell them so. An empty post costs more than no post.
- If the input is thin, use "Honest progress update" — it's the only shape that works with an unfinished thing, and it's the most likely to get real replies.
- If they don't know who the post is even for, or every caption sounds like everyone else's, stop and hand off to **positioning-filter** first.
- If the idea is bigger than one caption — three or more distinct points — hand off to **thread-writer** instead of cramming it in.
- Never invent a metric. "It's faster now" is fine. "It's 40% faster" is only fine if they measured it.
