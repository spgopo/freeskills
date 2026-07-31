---
name: learn-anything
description: Teaches you a topic at your real level, with practice instead of a lecture. It finds out what you already know, shows you the shape of the thing before the details, gives you the five ideas that carry most of it, then a ladder of three exercises — 15 minutes, an hour, one evening — and ends with the misconception beginners in this topic almost always carry. Use when the user says "teach me", "explain X", "I want to learn", "help me understand", "I don't get how X works", "explain like I'm five", "where do I start with", "I need to learn this by Monday", "give me a crash course", or /learn-anything.
---

# Learn Anything — teach me properly, in short passes

Most explanations fail in one of two ways: they're pitched at the wrong level, or they're a wall of text with nothing to do at the end. This skill finds your actual starting point, gives you the shape before the details, and hands you three exercises you can do tonight. You finish knowing one real thing you can do, not one page you've read.

## Setup
None. This skill works out of the box.

## Steps

### 1. Find their real level — three questions, no more
Ask these together in one short message:

1. **What do you already know about this?** Even "nothing" is a useful answer.
2. **Why now?** What are you trying to do or understand — a job, a project, curiosity, a conversation you want to follow.
3. **How deep do you need to go?** Enough to hold a conversation / enough to make decisions / enough to do it yourself.

Then do the thing that actually calibrates level: **name one adjacent thing they probably do know and check.** "You've used a spreadsheet before — do formulas make sense to you?" Their yes or no tells you more than the self-assessment does. People underrate themselves constantly.

Say back their level in one line and start there. Never open with definitions if they're past that.

### 2. Give the shape before the details
Before any facts, give a **map in under 120 words**: what this thing is for, what the main pieces are, and how they connect. Then one honest analogy to something they already know from their answers in step 1.

Say what the analogy gets wrong. Every analogy leaks, and telling them where saves them a wrong belief later.

Finish this pass by asking: **"Does that shape make sense before I fill it in?"** Stop and wait. Do not continue if they say no — re-draw the map differently instead of explaining harder.

### 3. Teach the five ideas that carry 80% of it
Pick exactly five. Not seven, not twelve. The five that, if they only knew these, would let them follow most conversations and make most beginner decisions correctly.

For each one, in this order:
- **The idea in one sentence**, in plain words.
- **Why it exists** — what problem it solves. People forget facts and remember reasons.
- **One concrete example** with real details, not a placeholder.

Keep each idea under 100 words. Deliver them in **two passes, not one** — ideas 1 to 3, then stop and ask one check question. A real question with an answer, like "if X happened, which of these would explain it?" Not "make sense?" Then ideas 4 and 5.

If they get the check question wrong, that's the most useful moment in the session. Re-teach that one idea a different way before continuing.

### 4. Build the practice ladder — three rungs
This is the part that makes it stick. Three exercises, each concrete enough to start without asking a follow-up question.

- **Rung 1 — 15 minutes.** Something they can do right now with what's already on their computer or in the room. Guaranteed to work. The point is contact with the thing, not challenge.
- **Rung 2 — one hour.** They apply the five ideas to something of their own — their situation, their data, their project. This is where it stops being abstract.
- **Rung 3 — one evening (90 minutes).** A small complete thing, start to finish, with a visible result they could show someone. Something that would break if they'd misunderstood.

For each rung write: what to do, what "done" looks like, and the one place people get stuck plus how to get unstuck. If the topic suits it, the evening rung should end with something they can send to a real person.

### 5. Name the misconception
Every topic has one wrong belief that beginners carry for months and that quietly ruins their reasoning. Name it plainly:

> **What most beginners believe:** ...
> **What's actually true:** ...
> **How to tell the difference in practice:** ...

Pick the one that causes the most downstream damage, not the most common trivia error.

### 6. Give the next question, not a reading list
Close with one question they'll be ready to ask after rung 3, and one line on where that leads. A short list of two or three genuinely good sources is fine — never a wall of links. If you're not sure a resource still exists or is still accurate, say so rather than making one up.

## Output — save it
Write to `~/learning/<topic-slug>.md` (create `~/learning/` if needed) with:

```
# <Topic> — <their level, in three words>
## The shape
## The five ideas
## Practice ladder
### Rung 1 — 15 minutes
### Rung 2 — one hour
### Rung 3 — one evening
## The misconception
## The next question
## Notes to self
```

Leave the **Notes to self** section as an empty prompt: "What surprised you? What broke?" Tell them to add a line each time they come back.

Tell the user the path and say: do rung 1 now, while it's fresh. It's fifteen minutes.

## Example (input → output)
**Input:** "I keep hearing about DNS when people talk about websites and I nod along. I've got a domain I bought and can't point at anything. Teach me enough to stop being confused."

**Output (saved to `~/learning/dns.md`), compressed:**

> **Level:** owns a domain, has never touched a settings panel, needs to actually make it work.
>
> **The shape:** DNS is a phone book. Domains are names people remember; servers have numbers. DNS is the lookup that turns one into the other. Three pieces: the *registrar* (where you bought the name), the *nameservers* (which phone book is in charge), and the *records* (the actual entries). Where the analogy leaks: a phone book is one book, and DNS is thousands of copies that update at different speeds — which is why changes take hours to show up.
>
> **The five ideas:** (1) A record points a name at a number. (2) CNAME points a name at another name — this is what hosts hand you. (3) Nameservers decide which phone book counts, and only one can be in charge. (4) TTL is how long the old answer is cached, which is why you see the old site after changing it. (5) Nothing about DNS is instant, and that isn't a bug.
>
> **Check question after idea 3:** "You changed the record an hour ago and still see the old page. Which of the five explains it?"
>
> **Ladder:** *15 min* — run `dig yourdomain.com` and read what comes back; done when you can point at the A record. *1 hour* — point your domain at a free host and watch it resolve. *One evening* — put a one-page site on it and text the link to someone.
>
> **The misconception:** beginners think "it's not working" means they did it wrong. Usually it means TTL hasn't expired. The tell: check from your phone on mobile data — different network, different cache.

## Notes / edge cases
- The beginner failure mode this prevents: reading about a topic for hours and having nothing they can do. If there's no ladder, it isn't teaching.
- Never dump all five ideas at once. Two passes with a real check question in the middle is the whole method.
- If they answer "I know nothing" to everything, pick the level yourself from why they're learning it and say which level you picked, so they can correct you.
- If the topic is enormous ("teach me marketing"), narrow it to one usable slice and say what you cut. Teach that slice properly rather than surveying the whole field badly.
- If the topic is fast-moving or you're unsure a detail is current, mark it clearly rather than guessing — and hand off to **research-brief** for the current state of it.
- If they want to *build* the thing rather than understand it, teach rungs 1 and 2 fast and spend the time on rung 3.
