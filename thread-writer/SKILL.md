---
name: thread-writer
description: Turn one idea into an X thread or a long LinkedIn post that people actually read to the end. Builds a hook that makes a specific promise, one idea per line, a real example early so people trust you, and an ending that lands instead of trailing off. Use when the user says "write a thread", "turn this into a thread", "long LinkedIn post", "I have an idea but it's too big for one post", "how do I explain this in a post", "write this up as a thread", "make this into a post series", or "/thread-writer".
---

# Thread Writer — one idea, told so people finish it

A thread fails for one reason: somewhere in the middle, a line gives the reader permission to stop. This skill builds a thread where every line's only job is to pull them into the next one, opens with a promise it actually keeps, and puts something concrete near the top so the reader believes you before they've invested any time.

## Personalization
This skill works in *your* brand voice. Before running, load the brand profile at `~/.claude/brand-profile.md`.
- If it doesn't exist, run the **personalize** skill first (or just tell me your name, niche, offer, and audience — I'll create it).
- If a field this skill needs is blank, I'll ask one or two quick questions and save the answers back to the profile so you only answer once.
- Never invent facts or results about the user — use only what's in the profile, or ask.

## Steps

### 1. Find the ONE idea
Ask: "What's the one thing you want someone to walk away knowing?"

Then compress their answer to a single sentence. Say it back to them. If you can't get it to one sentence, they have two threads, not one — make them pick which one to write now.

Also ask, if it isn't obvious: "Did you actually do this, or are you explaining a thing you read?" A thread built on their own build, mistake, or number is worth ten built on general advice. Push them toward their own experience every time.

### 2. Gather the proof before writing a word
Ask for the concrete stuff:
- a number they actually measured (hours, dollars, attempts, users, days)
- a specific moment (the night it broke, the message from the first user)
- a before and after they can describe

Write these down first. They anchor the whole thread. If they have none, the thread will be generic — go back and pick a narrower idea they've actually lived.

Never invent a number. If there isn't one, use a specific description instead: "it took me five nights" is a number; "it kept crashing at the same screen every time" is a concrete detail. Both work. "It was really hard" does not.

### 3. Write the hook with a specific promise
The hook is one or two lines, and it has to promise something exact.

Test it against these:
- Does it say what the reader gets? "How I built a booking site in a weekend with no code" promises. "Some thoughts on building" doesn't.
- Is it specific enough to be falsifiable? Vague promises read as noise.
- Does it avoid the wind-up? Cut "I want to talk about", "Here's a thread on", "Let me tell you".
- Would a stranger with no idea who they are stop for it?

A good hook shape: a concrete outcome + the surprising constraint. "I built a working app in 6 nights and I still can't read code."

Write three hooks. Pick the strongest and say why in one line.

### 4. Build the body — one idea per line
Now write the middle. The rules are strict because this is where threads die.

- **One idea per line.** Never stack two thoughts in one line. If a line has an "and" joining two ideas, split it.
- **A blank line between every line.** White space is what makes it readable on a phone.
- **Concrete proof by line 3 or 4.** Put the number or the specific moment early. The reader is deciding whether to trust you in the first 15 seconds, not the last.
- **The retention rule:** read each line and ask "does this make me need the next one?" If a line resolves the tension completely, move the resolution later or cut the line. Every line ends slightly open.
- **No summarizing mid-thread.** "So as you can see" is where readers leave.
- Order the middle as a real sequence: what I thought → what happened → what I'd do differently. Story beats list. If it must be a list, make each item a small story.

Length: 6 to 12 lines for X, 8 to 15 short lines for LinkedIn. If it's longer than that, the idea wasn't one idea.

### 5. Land the ending
Most threads trail off into a weak "anyway, hope this helps." The ending should do one of three things, and only one:
- **Snap back to the hook.** Answer the promise directly and stop.
- **Hand them the smallest next step.** One action they could take tonight, described in one line.
- **Ask a real question.** Not "thoughts?" — something specific enough to answer in five words.

Then, if there's something to share, one CTA. On X that's a link or "reply and I'll send it." On LinkedIn, a comment keyword pulls more replies than a link. One ask only.

### 6. Format for the platform and read it back
- **X:** number nothing. Each line becomes its own post in the thread, under 280 characters each. Post 1 is the hook. The last post carries the CTA.
- **LinkedIn:** one single post. First two lines must work before the "see more" cut — put the hook and the promise there. Keep every line short.

Final check before saving:
- Cut the weakest line. There's always one.
- Any line that could be deleted without losing meaning gets deleted.
- Banned words: unlock, leverage, elevate, game-changer, journey, seamless, humbled, thrilled.
- Read it out loud. Any sentence you stumble on gets rewritten shorter.

## Output — save it
Write the finished thread to `~/threads/YYYY-MM-DD-<short-slug>.md` (create `~/threads/` if needed).

The file contains: the one-sentence idea, the platform, the chosen hook plus the two runners-up, the full thread formatted exactly as it should be posted (numbered posts for X, one block for LinkedIn), and the CTA.

Tell the user the path. Then give them the one next action: post it, then reply to every comment in the first hour — the replies are the point.

## Example (input → output)
**Input:** "I want to write a thread about how I built my portfolio site in a weekend with Claude Code even though I've never coded. It took like 9 tries to get the layout right."

**Output (saved to `~/threads/2026-07-30-portfolio-weekend.md`):**

One idea: *You don't need to know code — you need to be willing to say what's wrong nine times.*

Hook:
> I built my portfolio site in a weekend. I have never written a line of code.
>
> The part nobody tells you: it took 9 tries to get one layout right, and that's the normal number.

Body (excerpt):
> Try 1 was ugly. I told it "the header feels cramped."
>
> Try 4 was worse. I told it that too.
>
> I never opened the code. Not once.
>
> Every round I said one specific thing I could see with my own eyes.
>
> That's the entire skill. Describing what's wrong, out loud, in normal words.

Ending:
> The site is live. It took a weekend and 9 rounds of me complaining in plain English.
>
> If you've been waiting until you learn to code: you're waiting for the wrong thing.
>
> Comment SITE and I'll send you the exact prompts I used.

## Notes / edge cases
- The failure mode this prevents: a thread that's really five threads mashed together. One idea, or nobody finishes it.
- If they have no proof, no number, and no story of their own, the thread will be generic advice. Say so and help them narrow to something they actually did.
- If the idea fits comfortably in one post, tell them to use **caption-writer** instead. Padding a small idea into a thread is worse than posting the small idea.
- If the idea is really a client result, hand off to **case-study** — that format converts far better for a win.
- If the hook keeps coming out generic no matter how many you write, the problem is positioning, not copy. Hand off to **positioning-filter**.
