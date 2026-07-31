---
name: case-study
description: Turn one win into a short case study you can send to a prospect or post publicly — where they started, what you built, what changed, and one honest line about the hard part. Works for a paid client, a free build, or your own project. Never invents numbers. Use when the user says "write a case study", "turn this into a case study", "I finished a client project, now what", "how do I show this work", "write up this result", "proof for my portfolio", "something I can send to a prospect", or "/case-study".
---

# Case Study — turn one win into something you can send

A finished project sitting in a folder does nothing for you. A short case study is the same work, told in a way that makes the next person want it. This skill turns one win into a page you can paste into a DM, drop on a portfolio, or post publicly — built around a real before and after, with no invented metrics.

## Personalization
This skill works in *your* brand voice. Before running, load the brand profile at `~/.claude/brand-profile.md`.
- If it doesn't exist, run the **personalize** skill first (or just tell me your name, niche, offer, and audience — I'll create it).
- If a field this skill needs is blank, I'll ask one or two quick questions and save the answers back to the profile so you only answer once.
- Never invent facts or results about the user — use only what's in the profile, or ask.

## Steps

### 1. Find out what kind of win this is
Ask which one it is, because it changes how it's written:
- **Paid client** — name them if you have permission, otherwise "a landscaping company in Denver." Specific and anonymous beats vague and named.
- **Free build or favor** — completely valid proof. Write it exactly the same way. Do not apologize for it being free, and do not mention that it was free unless they want to.
- **Their own project** — the client is themselves. The "before" is their own problem. This is the most common case for beginners and it works fine.

### 2. Interview them properly
This is the step that decides whether the case study is good. Ask these, one at a time, and push for specifics:

1. **"What was going on before? What was it costing them?"** Cost is the point. Hours a week, missed calls, money left on the table, a thing they dreaded doing. If they say "they didn't have a website", push: "and what happened because of that?"
2. **"What did you actually build?"** Plain words. Not a feature list — what it does for a human.
3. **"What's different now?"** The most important question. Ask it twice if the first answer is soft.
4. **"Is there a real number?"** A number they or the client actually observed. If not, that's fine — say so and move on.
5. **"What was the hardest part?"** They'll want to skip this. Don't let them.

If they give three-word answers, ask "what happened right before you started?" — the origin story usually contains the whole before-state.

### 3. Handle the numbers honestly
Never invent a metric. Not a rounded one, not an "estimated" one, not a plausible one. One fake number in a case study poisons the whole thing, and a prospect who catches it is gone.

Use, in this order of preference:
1. **A measured number.** "Went from 4 inquiries a month to 19."
2. **A time number.** Almost always available and almost always ignored. "Took 6 days from first call to live site." "Cut a 3-hour weekly job to about 10 minutes."
3. **A countable fact.** "Handles 60 bookings a week now." "First 12 signups in the first day."
4. **A concrete before/after description.** When there's no number at all: "Before, every booking was a phone call during their workday. Now people book themselves at 11pm and the owner sees it in the morning." This is genuinely strong. Do not treat it as a fallback that needs apologising for.

If the user offers a number they can't point to a source for, ask "where did that come from?" If the answer is a guess, downgrade it to a description.

### 4. Write it
Five sections, short. The whole thing should be readable in under 90 seconds.

1. **The one-line summary.** Who it was for, what they got, the strongest true fact. This line is what gets read in a DM preview, so it carries the most weight.
2. **Where they started.** Two to four sentences. The situation and what it was costing. Written so the reader recognises their own situation in it — that recognition is what makes them keep reading.
3. **What got built.** Two to four sentences. What it is and what it does for a person. No technical stack talk. If the user wants to name tools, one sentence maximum.
4. **What changed.** The number or the concrete before/after. Be exact about what is and isn't measured. "In the first month" is better than "since launch."
5. **The honest line.** One sentence about what was hard, what took longer than expected, or what they'd do differently. This is the section people cut and it's the section that makes the rest believable. Keep it to one line and don't turn it into an apology.

Then, if it's for a prospect, one closing line: what someone should do if they want the same thing. One ask.

### 5. Make the two versions
Same content, two shapes:
- **The send version** — for a DM or an email. Tighter. Cut section headings, keep it to about 150 words, lead with the one-liner. Ends with the ask.
- **The post version** — for LinkedIn or a portfolio page. Keep the sections, add line breaks between every idea, lead with the before-state rather than the summary because that's what stops a scroll.

### 6. Get permission clear
Before it goes anywhere public, check: does the client know this is being published, and are they okay with their name on it? If the answer is "I haven't asked", write the anonymous version and give them one line to send:

> Quick one — I'd like to write up what we built as a short case study. Happy to keep your name out of it, or use it if you're fine with that. Either way, no pressure.

Never publish a client's name or numbers without a clear yes.

## Output — save it
Write the result to `~/case-studies/<client-or-project-slug>.md` (create `~/case-studies/` if needed).

The file contains: the one-line summary, all five sections, the tightened send version, the post version, a note on what's measured versus described, and the permission status.

Tell the user the path, then the one next action: send the short version to one person this week who has the same problem the client had.

## Example (input → output)
**Input:** "I built a booking page for a mobile dog groomer I know. She was taking every booking over the phone while driving. She's not paying me, it was a favour. It went live 3 weeks ago and she says she's had about 30 bookings through it."

**Output (saved to `~/case-studies/mobile-dog-groomer.md`):**

**One line:** A mobile dog groomer was taking every booking by phone while driving between jobs. Now clients book themselves — around 30 in the first three weeks.

**Where they started:** She ran her whole calendar off her phone, between appointments. Calls came in while she was driving or mid-groom, so she missed them, and missed calls are missed jobs. She was writing bookings on paper at traffic lights.

**What got built:** A one-page booking site. Clients pick a service, pick a slot, leave a number. She sees it on her phone. Nothing to install, no account for anyone to make.

**What changed:** In the first three weeks she's had about 30 bookings come through the page. She counts them herself; that's her number, not a tracked one. She's stopped taking booking calls while driving.

**The honest line:** The first version had her whole week visible and she hated it — she only wanted to show three days out. Took four rounds of me changing it before it felt right to her.

## Notes / edge cases
- The failure mode this prevents: a portfolio full of screenshots with no story, which tells a prospect nothing about whether it would work for them.
- If there's no number and no visible change, it's too early. Tell them to wait two weeks and ask the client one question: "has anything been different since?"
- Free work and personal projects count. A prospect cares whether you can do the thing, not whether the last person paid.
- If they have a happy client but no quote from them, this pairs with **testimonial-ask** — run that next and drop the quote in.
- If they don't yet know who they'd even send this to, hand off to **positioning-filter** first.
- One case study per project. Do not merge three small wins into one page; it reads as padding.
