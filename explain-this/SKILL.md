---
name: explain-this
description: Paste any file, folder listing, snippet, config, or line you don't understand and get a plain-English explanation at total-beginner level — what it is, what it does, why it exists, and what would happen if it vanished. Ends with the one thing worth understanding and the one thing safe to ignore. Use when the user says "what is this file", "explain this", "what does this do", "what am I looking at", "I don't understand my project", "what's package.json", "why are there so many files", "is this important", "can I delete this", "walk me through my folder", or "/explain-this".
---

# Explain This — make your own project stop being scary

Your project folder fills up with files you never asked for and don't recognize, and it starts to feel like someone else's machine. Paste any of it here and get a plain explanation: what it is, what it does, why it's there, and whether you'd ever touch it. The goal is not to make you a programmer. It's to make you comfortable in your own build.

## Setup
None. This skill works out of the box.

## Steps

### 1. Take whatever they paste
Accept any of it: a whole file, a folder listing, five lines of code, a config, an error, a single word they saw. If they name a path instead of pasting, read the file yourself.

If they paste something enormous, don't explain every line. Explain the file's job, then the three or four parts that actually matter to them. Line-by-line explanation of a 400-line file teaches nothing.

If they paste with no question at all, assume the question is "what is this and should I care."

### 2. Answer the five questions, in this order
Always these five, always short. Headers, not paragraphs.

- **What this is.** The category, in one clause. "A settings file." "A list of the outside tools your project borrows." "The actual page people see."
- **What it does.** The job it performs while the project runs, in one or two sentences. Use an everyday comparison only if it's genuinely accurate — a bad metaphor is worse than none.
- **Why it exists.** Who or what put it here and what asked for it. Beginners assume every file was a decision they made. Most weren't — a tool created it. Say so, because it's a relief.
- **What happens if it vanished.** Be specific and honest. "Nothing, it's a cache and it rebuilds." "The site stops loading entirely." "Your styles disappear but the text stays." This is the question they're really asking when they ask if a file is important.
- **What you'd actually change in here.** Point at the two or three lines or values a non-coder would ever realistically edit — the title, the color, the text, the link. Say the rest is machinery.

### 3. Set the beginner level correctly
Rules for the whole explanation:
- Define a technical term in one short clause the first time it appears, then use it normally. Don't define it twice.
- Never say "simply," "just," or "obviously."
- Concrete over general. "This line sets the tab title you see at the top of the browser" beats "this handles metadata."
- Skip anything that's true but useless to them. They don't need to know what a bundler is to run their site.
- Never imply they should learn to write this. They're the director.

### 4. Flag anything that deserves a flag
Only when it applies, one line each:
- Something in here is a secret — a key, a password, a token — and shouldn't be posted publicly or pasted into a chat.
- This file is generated automatically, so editing it by hand gets overwritten.
- This file is safe to delete and will come back on its own.
- This file is the one that matters most in the whole folder.

### 5. Close with the two lines
End every explanation with exactly two lines, labeled:

- **Worth understanding:** the one idea in here that will pay off across every future project. Not the most complex thing — the most useful. "Every page you build has a `<head>` for the browser and a `<body>` for the human."
- **Safe to ignore:** the one thing they should stop looking at. Give them permission explicitly. "You never need to open node_modules. Ever. It's just downloaded tools."

Two lines, no more. That's the takeaway they'll actually keep.

## Output — save it
Create `~/claude-explained/` if needed. Save as `~/claude-explained/<name>.md`, named after what they asked about — `package-json.md`, `my-project-folder.md`, `index-html.md`.

The file holds: what they pasted (trimmed if huge), the five answers, any flags, and the two closing lines.

Tell them the path, then the one action: nothing to do. This one is for reading. Say that plainly so they don't sit there waiting for a task.

Mention once that the folder becomes their personal glossary, in their own words, about their own project.

## Example (input → output)

**Input:** "There's a file called package.json in my folder that I never made. Am I supposed to know what this is? Can I delete it?"

**Output (saved to `~/claude-explained/package-json.md`):**

**What this is:** The ID card for your project. A short list that says what your project is called and which outside tools it borrows.

**What it does:** When you or Claude starts your project, the computer reads this file first to find out what needs loading. It also stores shortcut commands — that's why typing `npm run dev` works.

**Why it exists:** You didn't make it. A tool created it automatically the first time your project was set up. Almost every project on earth has one.

**If it vanished:** Your project would stop running. It wouldn't know what to load or what the shortcut commands mean. So no, don't delete it — but it's easy to recreate if you ever did.

**What you'd actually change in here:** Realistically, one line: `"name"`. That's your project's name. The `"scripts"` section lists your shortcut commands, so it's worth a look to see what you can type. Everything under `"dependencies"` is managed by tools — leave it alone and let Claude edit it.

**Worth understanding:** Your project borrows other people's tools instead of building everything from scratch, and this file is the borrowing list. That's true of every project you'll ever make.

**Safe to ignore:** The version numbers with the `^` symbols. You will never need to think about those.

## Notes / edge cases
- The failure this prevents is a beginner feeling like a tourist in their own folder and never opening it again. Comfort is the deliverable.
- If they paste something with a real secret in it — an API key, a password — say so immediately, before explaining anything else, and tell them to treat that key as exposed.
- If they paste something genuinely unimportant, say it's unimportant in the first line. Don't write five sections about a lock file to seem thorough.
- If the file is huge and generated, explain the category once and tell them nobody reads these, including professionals.
- If they're pasting an error rather than a file, hand off to **error-decoder** — that one gives them a fix sentence, this one only explains.
