---
name: email-writer
description: Writes the email you've been putting off — chasing an unpaid invoice, saying no, apologizing for a mistake, asking for a raise or a rate rise, the third follow-up, or delivering bad news. Asks three quick questions (who they are to you, what you want to happen, how blunt you can be) and hands back a short email with one clear ask near the top, in your voice. Use when the user says "write an email", "help me write this email", "I need to email someone", "how do I say no to this", "chase an invoice", "they haven't paid me", "follow up email", "I need to apologize", "ask for a raise", "email I've been avoiding", "I don't know how to word this", or /email-writer.
---

# Email Writer — the one you've been avoiding

Most hard emails don't get sent because the person can't find the tone. So they write four paragraphs of throat-clearing and bury the actual ask in the last line, where nobody reads it. This skill does the opposite: one ask, near the top, in plain words that sound like you. You get a subject line and a body you can paste and send.

## Personalization
This skill works in *your* brand voice. Before running, load the brand profile at `~/.claude/brand-profile.md`.
- If it doesn't exist, run the **personalize** skill first (or just tell me your name, niche, offer, and audience — I'll create it).
- If a field this skill needs is blank, I'll ask one or two quick questions and save the answers back to the profile so you only answer once.
- Never invent facts or results about the user — use only what's in the profile, or ask.

## Steps

### 1. Name the email type
Read what the user gave you and sort it into one of these six. If it's none of them, treat it as a general ask and keep going.

- **Chasing money** — an invoice is late.
- **Saying no** — turning down work, a favour, a call, a discount.
- **Apologizing** — you missed something, broke something, were late.
- **Asking for more** — a raise, a rate increase, better terms.
- **Third follow-up** — you've chased twice and heard nothing.
- **Bad news** — a delay, a price rise, a cancellation, a firing.

Say which one you picked in one line. Each type has a rule you must follow, listed in step 4.

### 2. Ask the three questions
Ask these together, in one short message. Never ask more than three.

1. **Who is this person to you?** (client who pays you, boss, someone you need again later, someone you'll never deal with again)
2. **What do you want to actually happen after they read it?** One outcome. "Pay the invoice by Friday." "Agree to £X." "Stop asking."
3. **How blunt can you be?** Warm / straight / firm. If they don't know, use straight.

If the user already told you these in their first message, don't ask again — say what you inferred and carry on.

### 3. Get the facts you can't invent
Only ask for what you genuinely need to write it: amounts, dates, invoice number, what was promised, what went wrong. If a fact is missing, write `[FILL IN]` in the draft rather than making something up. Never invent a number, a date, or a promise.

### 4. Write the email — one ask, near the top
Structure every email like this:

- **Subject line:** plain and specific. "Invoice 104 — now 3 weeks overdue" beats "Quick question."
- **Line 1:** one sentence of context so they know why you're writing.
- **Line 2 or 3:** the ask. What you want, and by when. This is the rule — the ask never lives at the bottom.
- **Middle:** the short reason, only if it helps them say yes.
- **Close:** one line, no grovelling.

Keep it under 150 words. Short paragraphs, one to three lines each. No "I hope this email finds you well." No "just circling back." No apologising for existing.

Type rules, apply the one that matches:
- **Chasing money:** state the amount, the invoice number, and the original due date. Ask for a payment date, not for "an update." Stay neutral — assume it's an oversight until proven otherwise. Add the next step if it's ignored only on a third chase.
- **Saying no:** say no in the first two lines. Don't leave a door open you don't mean. One sentence of reason, no essay. Offer an alternative only if you actually want to.
- **Apologizing:** own it plainly, no "if you felt." Say what you're doing about it. One apology, not four. Don't explain more than one sentence' worth.
- **Asking for more:** lead with what you want and the number. Then two lines of evidence — results, extra scope, market rate. Never apologise for asking. Never open with "I know times are tough."
- **Third follow-up:** name the fact that it's the third. Make it easy to close the loop: "If this is no longer happening, just reply 'no' and I'll close the file." That line gets more replies than any chase.
- **Bad news:** the news goes in the first sentence, before the reason. Then what you're doing about it, then what you need from them. Never bury it in paragraph three.

### 5. Match their voice
Rewrite once using the brand profile's tone, loved words, and banned words. Read it back as if you're the recipient and ask: is the ask obvious in the first five seconds? If not, move it up.

### 6. Give them a softer and a harder version of one line
Pick the single line that carries the most risk — usually the ask. Offer two alternatives: one warmer, one firmer. One line each. Let them swap it in without rewriting anything else.

## Output — save it
Write the email to `~/emails/<short-slug>-<YYYY-MM-DD>.md` (create `~/emails/` if it doesn't exist). Include: the subject line, the full body, and the softer/firmer swap lines at the bottom under a `## Swaps` heading.

Tell the user the path and say: paste it, replace any `[FILL IN]`, send it today. Nothing about a hard email gets easier by sitting overnight.

## Example (input → output)
**Input:** "A client owes me £1,800 from an invoice I sent five weeks ago. I've chased once. I want to work with them again so I don't want to be aggressive."

**Output (saved to `~/emails/invoice-104-chase-2026-07-30.md`):**

> **Subject:** Invoice 104 — £1,800, now 5 weeks overdue
>
> Hi Sam,
>
> Invoice 104 for £1,800 was due on 25 June and is still showing unpaid on my side.
>
> Can you confirm a payment date this week? If it's stuck in your finance system, tell me who to send it to and I'll chase it there instead.
>
> Happy to keep things moving on the next project once this one's closed out.
>
> Thanks,
> Alex
>
> **## Swaps**
> - Warmer ask: "No rush today — just let me know roughly when it's likely to land."
> - Firmer ask: "I need a payment date by Friday before I schedule any further work."

## Notes / edge cases
- The beginner failure mode this prevents: writing 300 words of apology and burying the ask in the last line. If the draft doesn't state the ask by line three, rewrite it.
- If the input is thin ("I need to email my boss"), ask the three questions and stop. Don't guess at what the relationship is.
- If the email involves a contract, a dismissal, money owed over a long period, or anything that could end up in a legal process, write it plainly and add one line: "This one is worth a professional's eyes before you send it." Don't give legal advice.
- If the user is angry, write the sendable version, not the honest one. Offer to save the angry one to a separate file they don't send.
- If the message they received is long and confusing, run **doc-digest** on it first, then come back here to reply.
- If the draft reads stiff or corporate after all this, run **rewrite-plain** on it.
