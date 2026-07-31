---
name: simple-tracker
description: Build a small personal tracker or dashboard that runs entirely in your browser and saves your data on your own machine — habits, workouts, client pipeline, reading list, money in, anything you currently keep in a messy spreadsheet. No login, no database, no monthly bill, one HTML file you open like a bookmark. Use when the user says "build me a tracker", "habit tracker", "I want a dashboard for my stuff", "replace my spreadsheet", "something to log my workouts", "track my clients", "personal dashboard", "app to keep track of", "reading list app", or types /simple-tracker.
---

# Simple Tracker — one file, your data, no bill

Most of what people want from an app is a list they can add to and one number that tells them how it's going. That doesn't need a login, a database, or $12 a month — it needs one HTML file that saves to your own browser. This builds that. It's also the best second project a beginner can do, because you use it every day, so you actually notice what to improve.

## Setup
None. This skill works out of the box.

## Steps

### 1. Pick what to track
Ask what they're keeping in their head or in a messy spreadsheet right now. If they don't have an answer, hand them this menu and let them pick one. Each comes with a starter prompt they can use as the description:

- **Habit tracker** — "One row per habit, a checkbox for each day of the current week, and a big number at the top showing my longest current streak."
- **Workout log** — "I add an exercise with sets, reps, and weight. It shows my last five sessions and, at the top, the total weight I moved this week compared to last week."
- **Client pipeline** — "Each client is a card with a name, what they're paying, and a stage: lead, talking, sent proposal, closed, dead. Big number at the top is total money in the 'sent proposal' and 'closed' columns."
- **Reading list** — "I add a book with a title and author. Each one is want-to-read, reading, or finished. Top number is how many I've finished this year."
- **Money in** — "I log a payment with who, how much, and the date. Top number is this month's total next to last month's total."
- **Content log** — "I log a post with the platform, the date, and the hook. Top number is how many I've published in the last 30 days."

Whatever they pick, ask one follow-up: "What's the one number you'd want to see the second you open it?" That answer becomes the top of the page and shapes everything else.

### 2. Lock the shape — one add, one list, one number
Every good small tracker is the same three parts. Say them out loud so the user learns the shape, not just gets a file:

1. **One thing you add.** A single row of inputs at the top, or one button that opens a small form. Two or three fields maximum. If adding an entry takes more than about eight seconds, they'll stop using it inside a week, and an unused tracker is worse than the spreadsheet.
2. **One list you see.** Newest first. Each row shows only what they'd want to scan, plus one way to edit and one way to delete. Nothing else.
3. **One number at the top that tells you how you're doing.** Big, unmissable, and honest. Not three charts. One number, with one small line of context under it — "12 this month · 9 last month."

Push back on scope creep here, once and clearly. Beginners ask for tags, filters, search, categories, charts, and reminders in the first sitting, then never finish. Build the three parts, use it for a week, then add the one thing they actually missed. That's the loop.

### 3. Get the data model right, then say it in plain English
Before building, tell them exactly what one entry holds, in words:

> "One entry is: a name, a number, a date, and a status. That's it. Everything on the page is built from those four things."

Then decide the small stuff up front:
- What counts as a duplicate, if anything.
- What order the list sorts in.
- What the number at the top is actually calculating, said as a sentence: "how many entries have status 'finished' and a date in this year."
- What the page shows when there's nothing in it yet — the empty state. This matters more than people think, because it's the first thing they'll ever see. Write one friendly line plus a hint of what to type.

### 4. Build it
One file. Bake in every one of these:

- One self-contained `index.html`. No build tools, no external JS libraries, no frameworks, no backend, no database.
- **Save to `localStorage`.** All data lives in the browser under one clearly named key. Read it on load, write it on every change. Store it as JSON.
- Google Fonts is the only external resource. One display font for the big number and headings, one body font for the list.
- Restrained palette: one accent plus neutrals. **Never** the generic purple-to-blue AI gradient. The accent belongs on the add button and the top number, nowhere else. If `~/.claude/design.md` exists, read it and follow that palette, font pairing, and spacing.
- Mobile-first. They will use this on their phone. Inputs at least 48px tall, tap targets at least 44px, nothing scrolls sideways at 375px wide, and the add form is reachable with a thumb.
- **Readable without JavaScript.** With scripts off the page still shows the title, what the tracker is for, and the empty-state explanation, rather than a blank white screen.
- Animate with transforms and opacity only. A new row can fade and slide in over about 150ms. No animated blur, no noise filters, no marquees, nothing looping.
- Real copy — the actual labels for their actual tracker. Never lorem ipsum.
- Icons inline SVG. Delete gets a small confirm so a mis-tap doesn't wipe a row.
- Viewport meta tag and a real `<title>`, so it looks right saved to a phone home screen.
- **Export and import buttons.** Export downloads their data as a JSON file. Import reads one back in. This is the honest tradeoff of `localStorage`: the data lives in one browser on one device, and clearing browsing data can wipe it. Two small buttons make that survivable. Say this to the user plainly rather than hiding it.
- Keep the entire data shape and the top-number calculation in one clearly commented block near the top of the script, so it's obvious where to change things later.

### 5. Use it before you improve it
Tell them the last step, and mean it:

- Open the file, add three real entries right now, and check the top number is telling the truth.
- Bookmark the file, or on a phone add it to the home screen so it opens like an app.
- Use it for one week without changing anything.
- Then come back with one sentence about the thing that annoyed them most, and change only that.

That's the loop. Five to ten small rounds is normal and it is the workflow, not a sign anything went wrong. Also tell them: `/rewind` undoes any change, and "commit this as a checkpoint" makes a permanent save they can always get back to.

## Output — save it

Write the tracker to `~/tools/<tracker-slug>/index.html`.

Also write `~/tools/<tracker-slug>/notes.md` with: what one entry holds, what the top number calculates in plain English, the `localStorage` key name, the export/import warning about data living in one browser, and a short "next three things I might add" list — so when they come back in a week they don't start from a blank page.

Tell them both paths, then:

> "Open `~/tools/<tracker-slug>/index.html`, add three real entries, and bookmark it. Use it for a week before changing anything, then tell me the one thing that annoyed you."

## Example (input → output)

**Input:** "I keep my freelance clients in a Google Sheet and I never open it. I want to see what money is actually coming."

**Output (saved to `~/tools/client-pipeline/index.html`):**

- **One entry holds:** client name, monthly amount, stage (lead / talking / proposal sent / closed / dead), and the date added.
- **Add:** one row at the top — name, amount, a stage dropdown, and an "Add client" button. Under eight seconds.
- **List:** cards newest first, grouped by stage, with the amount on the right. Tap a card to change its stage. Small delete with a confirm.
- **The number:** `$4,300 in play` in big display type, with a smaller line under it: "3 proposals out · 2 closed · $1,800 already closed."
- **Empty state:** "Nothing here yet. Add the client you spoke to most recently."
- **Look:** bone background, near-black text, one deep green accent on the add button and the big number only. New cards fade and slide in over 150ms.
- **Data:** saved to `localStorage` under `client-pipeline-v1`. Export and Import buttons in the footer.
- `notes.md` warns that the data lives in this browser on this device, tells them to export once a month, and lists three possible next additions: a "last contacted" date, filtering out dead clients, and a monthly total.

## Notes / edge cases
- The beginner failure this prevents: designing a full app with login, database, and hosting for something one person will use, then never finishing it.
- `localStorage` is per-browser and per-device. Their phone and their laptop will hold different data, and clearing browsing data wipes it. Say this plainly and always ship export/import. Never imply it syncs.
- If they ask for accounts, sharing with a teammate, or access from two devices, that's a real database and a different project. Say so honestly instead of half-building it. Build the one-person version first — it usually turns out to be enough.
- If they list eight features in the first message, build the three-part shape and put the other five in the `notes.md` "next three things" list. They can have them; just not before they've used it.
- Run **mobile-check** on it after a week of real use, and **make-it-designed** if it works but looks like a spreadsheet with a font.
