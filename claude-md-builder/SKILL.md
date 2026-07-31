---
name: claude-md-builder
description: Build the CLAUDE.md memory file for a project so Claude stops forgetting your rules every time you open a new session. Interviews you about what the project is, the rules to always follow, what to never do, where files live, and how you want to be talked to — then writes a short CLAUDE.md into the project folder. Use when the user says "make a CLAUDE.md", "claude md builder", "set up project memory", "Claude keeps forgetting things", "how do I stop repeating myself to Claude", "Claude forgets what my project is", "give Claude rules for this project", "claude.md file", "quad md", or types /claude-md-builder.
---

# CLAUDE.md Builder — give Claude a memory for this project

Every new session, Claude starts blank. You re-explain the project, re-state your rules, and watch it make the same mistake it made yesterday. A `CLAUDE.md` file fixes that: it sits in the project folder and gets read at the start of every session. This skill interviews you and writes a short, sharp one.

Short is the whole point. A `CLAUDE.md` is a command center, not a life story. Every line you add competes for attention with every other line. A bloated file makes Claude worse, not better — the rules that matter get buried under the rules that don't.

## Setup
None. This skill works out of the box.

## Steps

### 1. Find the project and check what already exists
Run `pwd` to confirm the current folder, and list what's in it so you can describe the project back to the user accurately. Check whether a `CLAUDE.md` already exists here.

- If one exists, read it and tell the user you'll rewrite it, showing what you're keeping. Never silently overwrite.
- If the folder looks empty or unrelated to a project, ask one question: "Which folder is this project in?" Don't guess.

Tell the user in one line what you see: "This looks like a landing page project — one index.html and an images folder. Is that right?"

### 2. Interview — six questions, one at a time
Ask these one at a time and wait for each answer. Short answers are fine — you'll tighten them.

1. **What is this project, in one sentence?** ("A booking page for my dog-walking business.")
2. **Who is it for, and what's the one thing it has to do?** (This is the goal that settles arguments later.)
3. **What are the rules you want Claude to follow every single time?** Prompt them with examples: keep it one file, always show me a preview before changing anything, never add new pages without asking, use my colors.
4. **What should Claude never do?** Examples to prompt with: never delete files, never add a login system, never install anything, never change the copy without asking.
5. **Where do things live?** Which file is the real one, where the images are, what to ignore. If they don't know, look at the folder and propose it.
6. **How do you want to be talked to?** Plain English, no code shown unless asked, explain choices in one line, ask before big moves.

If an answer is vague, ask one sharpening question, not five. "Use my colors" becomes "Which colors? Paste the hex codes or describe them."

### 3. Cut it down before you write it
This is the step people skip. Out loud, apply three cuts:

- **Cut anything Claude would do anyway.** "Write clean code" and "be helpful" are wasted lines. Keep only rules that change behavior.
- **Cut anything that's true today but not next month.** Task lists and to-dos do not belong here. That's what a build log is for.
- **Cut duplicates.** If two rules say the same thing, keep the sharper one.

Target: under 40 lines. If it's longer, cut again. Tell the user what you cut and why, in one line each.

### 4. Write CLAUDE.md
Write to `CLAUDE.md` in the project folder, in this shape:

```markdown
# <Project name>

<One sentence: what this is and who it's for.>

## The goal
<The one thing this project must accomplish. Use this to settle any question about scope.>

## Always
- <rule>
- <rule>

## Never
- <rule>
- <rule>

## Where things live
- `<file>` — <what it is>
- `<folder>` — <what it is>

## How to talk to me
- <preference>
- <preference>
```

Use their words, not yours. If they said "don't make it fancy," write that, not "maintain visual restraint."

### 5. Prove it worked
A memory file you can't verify is a memory file you won't trust. Tell the user exactly how to test it:

1. Close this session and start a new one in this folder.
2. Type: "What is this project and what are my rules?"
3. Claude should answer from the file without you explaining anything.

If it doesn't, the file is in the wrong folder — Claude reads `CLAUDE.md` from the folder you started the session in. Tell them to check they opened Claude Code in the project folder.

### 6. Tell them how to grow it
One short note: when they correct Claude twice on the same thing, that correction becomes a line in `CLAUDE.md`. Not before. The file grows from real mistakes, not from imagining rules in advance.

## Output — save it
Write `CLAUDE.md` into the current project folder (the one from step 1). Print the full file back to the user in the chat, state the exact path, and give one next action: "Start a fresh session here and ask 'what are my rules?' to prove it loaded."

## Example (input → output)
**Input:** User has a folder with a one-page site for their dog-walking business. They keep having to re-explain that it must stay a single file and that Claude should never touch the pricing copy.

**Output (saved to `./CLAUDE.md`):**
```markdown
# Paws & Co. Booking Page

A one-page site where dog owners in my neighborhood book a walk. Built for phones first.

## The goal
Get a stranger from the top of the page to a filled-out booking form in under 30 seconds.

## Always
- Keep everything in one file: index.html. Styles and scripts go inline.
- Show me the page in the browser before you call anything done.
- Ask before changing any pricing text. Those numbers are set.

## Never
- Never add a second page.
- Never install anything or add a library.
- Never use stock filler text — write real copy or ask me for it.

## Where things live
- `index.html` — the whole site. This is the only file that matters.
- `photos/` — my dog photos. Use these, don't download new ones.

## How to talk to me
- Plain English. Don't show me code unless I ask.
- One line on why you made a choice, then move on.
```

## Notes / edge cases
- The number one failure mode is a `CLAUDE.md` that reads like a diary. If the user keeps adding, remind them: every extra line makes the important lines quieter.
- If the user has no project yet, don't write an empty file. Tell them to run **plan-first** and come back once there's something to describe.
- Rules that only apply to one task go in the prompt, not the memory file. Memory is for things true every session.
- If they want rules that apply to every project on their machine, that's a different file: `~/.claude/CLAUDE.md`. Mention it once, don't build it here.
- When a rule keeps getting ignored, it's usually too vague. Rewrite it as something checkable: "never add a page" beats "keep it simple."
