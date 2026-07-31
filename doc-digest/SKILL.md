---
name: doc-digest
description: Point it at a long document — a contract, a report, a paper, a huge email thread, a wall of text — and get back what actually matters: the decisions inside it, what it wants from you, the numbers, the dates, anything that looks like a trap, and the questions to ask before you sign or reply. Splits "what it says" from "what you should do about it" so you never confuse the two. Use when the user says "read this for me", "summarize this document", "what does this contract say", "I don't have time to read this", "what am I agreeing to", "is there anything dodgy in here", "explain this report", "TLDR this", "what does this mean", or /doc-digest.
---

# Doc Digest — what it says, and what to do about it

Long documents hide the important bits in the middle. The parts that cost you money are usually one sentence buried on page four. This skill reads the whole thing and pulls out the decisions, the dates, the numbers, the traps, and the questions you should ask before you reply or sign — with a hard line between what the document actually says and what you might do about it.

## Setup
None. This skill works out of the box.

## Steps

### 1. Get the document
Accept any of these:
- A file path (`.txt`, `.md`, `.pdf`, `.docx`, `.csv`, `.html`). Read it.
- Text pasted straight into the chat.
- A URL, if web access is available.

If it's a PDF over ten pages, read it in chunks and keep a running note as you go so nothing drops out. If you genuinely can't open the file, say so plainly and ask them to paste the text or save it as a `.txt` — don't guess at contents you haven't read.

### 2. Ask one question, only if the answer changes the output
Ask at most one thing: **"What are you about to do with this — sign it, reply to it, decide something, or just understand it?"**

That answer changes what you pull out. Signing means terms and traps. Replying means asks and deadlines. Deciding means options and trade-offs. If they already said, skip the question.

### 3. Read it in one pass and pull the six things
Work through the whole document and collect:

1. **What this document is** — one line. Who wrote it, who it's aimed at, what it's for.
2. **Decisions inside it** — anything that has already been decided, or that the document is asking to have decided. Quote the line.
3. **What it wants from you** — every ask, obligation, or action assigned to the reader. Include the implied ones.
4. **Numbers and dates** — money, percentages, quantities, deadlines, notice periods, renewal dates, term lengths. Copy them exactly. Never round, never estimate.
5. **Things that look like traps** — see step 4.
6. **What's missing** — things you'd expect a document like this to say that it doesn't. Silence is often the trap.

Quote the source line or page for anything important. If you're inferring rather than quoting, mark it `(inferred)`.

### 4. Run the trap sweep
Look specifically for these. They're where the damage usually lives.

- **Auto-renewal** and how much notice cancelling needs.
- **One-sided rights** — anything one party can do that the other can't (change price, end early, change terms).
- **Who owns what** at the end — work, data, accounts, files.
- **Exclusivity or non-compete** language.
- **Payment terms** — when, how late is late, what happens if it's late, who pays fees.
- **Liability and indemnity** — who carries the risk if it goes wrong.
- **Vague words doing heavy lifting** — "reasonable", "as needed", "from time to time", "at our discretion". These mean the other side decides.
- **Numbers that don't add up** or contradict each other elsewhere in the document.
- **Definitions that differ from plain English** — a document that defines "Services" narrowly on page one changes every later sentence.

List each trap with the quoted line and one plain sentence on why it matters. Don't dramatize. If a clause is normal and fine, say it's normal and fine.

### 5. Split "what it says" from "what you should do"
Write these as two separate, clearly headed sections. Never mix them.

- **What it says** is quotes and facts from the document only. No opinion.
- **What you should do about it** is your read: what to clarify, what to push back on, what to accept. Every item here must point back to a line in the section above.

### 6. Write the questions to ask before signing or replying
Five to eight questions, in the exact words the user could send. Each one targets a trap, a gap, or a number that isn't pinned down. Make them answerable with a sentence — not open-ended musing.

Then add a short **Worth asking a professional** list: anything involving law, tax, employment, immigration, medical matters, or serious money. Name the type of professional. Do not give legal or financial advice, do not tell them whether to sign, and do not say a clause is enforceable or unenforceable — that's not yours to call.

## Output — save it
Write to `~/digests/<doc-name>-<YYYY-MM-DD>.md` (create `~/digests/` if needed), with these headings in order:

```
# Digest — <document name>
## In one line
## What it says
### Decisions
### What it wants from you
### Numbers and dates
## Traps and things to watch
## What's missing
## What you should do about it
## Questions to ask before you sign or reply
## Worth asking a professional
```

Tell the user the path, and give them the single most important line from the whole document in your reply so they see it without opening anything.

## Example (input → output)
**Input:** A 14-page freelance contract from a new client. The user is about to sign it and wants to know what they're agreeing to.

**Output (saved to `~/digests/client-contract-2026-07-30.md`), compressed:**

> **In one line:** A 12-month freelance services agreement, £2,500/month, that renews itself and hands the client ownership of everything you make.
>
> **Numbers and dates:** £2,500/month · invoices paid "within 60 days of receipt" (p.4) · 12-month initial term from 1 Sept · 90 days' written notice to cancel (p.9).
>
> **Traps:**
> - "This Agreement shall renew automatically for successive 12-month terms" (p.9). You need to cancel 90 days before 31 Aug or you're locked in for another year.
> - "Payment within sixty (60) days of receipt of invoice" (p.4). That's you funding two months of work.
> - "All work product, including pre-existing materials incorporated therein, shall be the sole property of the Client" (p.6). As written, that reaches your own templates you brought with you.
>
> **What you should do about it:** ask for 30-day payment terms, carve your own pre-existing templates out of the ownership clause, and put a calendar reminder for 1 June for the renewal notice.
>
> **Questions to ask:** "Can we move payment terms to 30 days?" · "Can we add: pre-existing materials owned by the Contractor remain the Contractor's property, licensed to the Client?" · "Is the 90-day notice negotiable to 30?"
>
> **Worth asking a professional:** the ownership and indemnity clauses on p.6 and p.11 — a contract solicitor, before you sign.

## Notes / edge cases
- The beginner failure mode this prevents: skimming a long document, seeing nothing scary, and signing. The scary part is almost never written in a scary way.
- If the document is thin or vague, say so — "there isn't much here" is a real finding. Don't pad the digest to make it look thorough.
- Never invent a clause, a number, or a page reference. If you can't find something you'd expect, put it under **What's missing**, not under what it says.
- Never advise on whether to sign, whether a clause is legal, or what a court would do. Flag and route to a professional instead.
- If it's a research paper rather than a contract, swap the trap sweep for: sample size, what was actually measured, who funded it, and whether the conclusion is wider than the data supports.
- If reading it leaves the user stuck between choices, hand off to **decision-helper**. If they need to reply to it, hand off to **email-writer**.
