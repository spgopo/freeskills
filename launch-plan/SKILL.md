---
name: launch-plan
description: Plan a simple launch that creates a burst of sales for something you built, sized to the audience you actually have right now. Picks the launch type that fits your stage, sets a real date and a real number to aim at, and writes a day-by-day timeline plus a checklist of what you need to make. Use when the user says "I'm launching X", "plan my launch", "how do I launch this", "I built something and want to sell it", "waitlist strategy", "should I do a lifetime deal", "I want a burst of sales", or "/launch-plan".
---

# Launch Plan: pick the launch that fits your stage, then run it day by day

A launch is a short window where you point everything you've got at one offer, so the sales land together instead of dribbling in. This skill picks the right kind of launch for where you are, sets the date and the number, lists what you need to make, and writes out what you do each day.

One thing to be straight about up front. A launch is a spike, not your engine. It concentrates demand you already built into a few days. It doesn't replace showing up and making the offer the rest of the year.

## Personalization
This skill works in *your* brand voice. Before running, load the brand profile at `~/.claude/brand-profile.md`.
- If it doesn't exist, run the **personalize** skill first (or just tell me your name, niche, offer, and audience, and I'll create it).
- If a field this skill needs is blank, I'll ask one or two quick questions and save the answers back to the profile, so you only answer once.
- Never invent facts or results about the user. Use only what's in the profile, or ask.

## Steps

### 1. Get the five answers
Pull what you can from the profile first, then ask for the rest.

1. **What are you launching?** A product, a service, a cohort (a group that starts on the same day), a tool, a community.
2. **What stage is it at?** Idea, building, or built and ready to sell.
3. **How big is your audience right now?** Email list size, follower count, or "basically none yet." This one changes the plan more than anything else, so get a real number.
4. **Do you have a date in mind, or should I pick one?**
5. **What's the goal?** A number of sales, a dollar figure, or a number of signups.

If the offer and price aren't in the profile and this launch is for them, capture them now and save them back.

### 2. Pick one launch type, and say why
Recommend one. Don't hand over a menu.

- **Pre-sell.** Selling it before you've built it, at a lower founder price. Right when the thing isn't built yet, or you want proof people will pay before you spend six weekends on it. If nobody buys, you just saved yourself the build.
- **Waitlist.** A signup list of people who want in before the doors open. Right when it's built or nearly built and you want to stack up interest, then open to that list first.
- **Directory launch.** Posting to a place where people go to find new tools, like Product Hunt, a relevant subreddit, or a community. Right for a tool or app people can try on their own without you.
- **Limited-time or lifetime deal.** A price or a window that ends on a set date. A lifetime deal means they pay once instead of monthly. Right when it's built, you have some audience, and you want cash and momentum now.

If the audience is basically none, say it plainly: a launch to nobody is just a quiet day. Then give them the honest version instead. Either pre-sell to a small warm list and direct messages (warm means people who already know you), or spend the pre-launch window building a waitlist first. Don't promise a spike that the reach can't produce.

### 3. Set the date and the number
Pick a launch date far enough out to make the assets and warm people up. One to three weeks is usually right.

Write the goal as one concrete number. "30 pre-sales." "$5,000." "150 waitlist signups." A launch without a number is a wish, and you won't know afterward whether it worked.

Sanity-check the number against real reach. A spike is a small percentage of the people who see it, not a miracle.

### 4. List what you need to make
Keep this short. The minimum that makes the launch work, not an agency deliverable list. The usual set:

- **The page where people buy or sign up.** A sales page, a waitlist page, or the directory listing.
- **Two or three pre-launch teasers.** Posts or emails that build curiosity without selling yet.
- **The launch-day announcement.** The big "it's live" message.
- **One or two mid-launch messages.** Proof, or an answer to the objection you keep hearing.
- **The last-chance message.** Sent when the window is about to close.
- **The checkout link.** The link that actually takes money. Pull it from the profile if it's set.

Mark each item as *have* or *need*. Then offer to draft any of the messages in their voice.

### 5. Write the day-by-day timeline
Work backward from launch day, and lay it out as dated lines (Day -7, Day -3, Day 0, Day +1) with one or two concrete actions each. The shape:

- **Before:** warm people up. Teasers, behind the scenes, "something's coming," open the waitlist. Build interest, don't sell yet.
- **Launch day:** the announcement goes everywhere at once, pointing at one link. Reply to every comment and message.
- **The open days:** one message a day, new angle each time. Proof, then an objection, then a story, then the deadline getting close. Keep making the offer.
- **Close day:** last-chance messages, the deadline lands, the window shuts.
- **After:** thank the buyers, deliver, and write down what worked for next time.

### 6. Protect the deadline
Say this out loud to them before you save the plan. Most sales land in the final 24 hours. If you extend the deadline, you teach people your deadlines aren't real, and the next launch converts worse. Pick a date you're willing to hold.

## Output: save it
Write the plan to `~/launches/launch-<offer-slug>-<YYYY-MM-DD>.md` (create `~/launches/` if needed).

The file contains: the launch type and why it fits, the date, the number, the checklist with have or need marked on each line, and the day-by-day timeline.

Tell them the path, then give one next action: draft the first pre-launch teaser now, while it's fresh.

## Example (input → output)
**Input:** "I built a Notion template pack for freelancers. It's done. I've got about 1,200 email subscribers and I post on LinkedIn. I want to make some real money off it this month."

**Output (excerpt from `~/launches/launch-freelancer-template-pack-2026-07-21.md`):**

> **Launch type: limited-time deal.** It's built, you've got 1,200 people who already know you, and you want cash now. A 5 day window with a real deadline turns that list into a spike.
>
> **Date:** opens Monday July 21, closes Friday July 25 at midnight.
> **Goal:** 60 sales.
>
> **Checklist**
> - [have] The template pack and the checkout link
> - [need] Sales page with the price and the deadline on it
> - [need] 3 teasers this week
> - [need] Launch-day email and LinkedIn post
> - [need] Daily emails Tuesday to Friday
>
> **Timeline**
> - **Day -5 to -1:** tease it. "Dropping something Monday for freelancers who hate admin." One LinkedIn post, one email.
> - **Day 0 (Mon):** it's live. Email, LinkedIn, stories. One link. Reply to everyone.
> - **Day +1 (Tue):** proof email. Screenshots of the templates in use.
> - **Day +2 (Wed):** objection email. "Is it worth it if I already use Notion?"
> - **Day +3 (Thu):** story email, plus "48 hours left."
> - **Day +4 (Fri):** two last-chance emails. Closes at midnight. Don't extend.
> - **Day +5:** thank the buyers, deliver, write down what converted.

## Notes / edge cases
- **Don't over-build the assets.** Launches fail from no audience or no urgency. They don't fail from a missing seventh email. Ship the minimum and go.
- **Small list, smaller goal.** 200 subscribers and a $50 product means the honest number is a handful of sales, and a handful of sales is a real win when it's your first one.
- **A quiet launch isn't a verdict on the product.** It usually means not enough people saw it. Check reach before you rebuild anything.
- **Keep going after it closes.** The spike ends, the offer stays live. Go back to making it every week.
- If you just built the thing and haven't sold it yet, run **first-product** first, then come back here to launch it.
- Once it's live and someone replies, **first-customer-closer** handles the conversation.
