# Doc Digest

Point it at a long document and get back the decisions, the numbers, the dates, and the traps.

Long documents hide the expensive parts in the middle. This skill reads the whole thing and pulls out what matters, with a hard line between **what it says and what you should do about it** — quotes on one side, your options on the other, so you never confuse the two.

## Install

1. Copy the `doc-digest` folder into your Claude Code skills directory:
   ```bash
   cp -r doc-digest ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/doc-digest`.

## How to use

No setup needed. Type `/doc-digest` and give it a file path, a URL, or just paste the text. It asks one question — are you signing it, replying to it, deciding something, or just trying to understand it — because that changes what it pulls out.

You get back a one-page digest saved to `~/digests/`: what the document is, what it wants from you, every number and date, the clauses worth worrying about, what's suspiciously missing, and the exact questions to send back before you sign. It won't give you legal or financial advice — it flags the parts worth putting in front of a professional.
