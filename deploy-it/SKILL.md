---
name: deploy-it
description: Put whatever you just built on a real public web address for free, one click at a time, and save the link so you build a list of things you've shipped. Covers the GitHub step in plain English and fixes the three things that actually break for beginners. Use when the user says "/deploy-it", "put this online", "how do I get this on the internet", "deploy my site", "publish my page", "I need a link I can send someone", "make this live", "host my website free", "get this off my computer", "how do I share what I built", or "my site is live but the page is blank".
---

# Deploy It — from a file on your laptop to a link you can text

Right now the thing you built only exists on your computer. Nobody can see it, which means it doesn't count yet. This gets it onto a real web address for free, in about ten minutes, without you understanding anything about servers. Then you send that link to one person today.

## Setup
None. This skill works out of the box.

## Steps

### 1. Find what we're shipping and set expectations
Look in `~/sites/` and `~/games/` for folders with an `index.html`. If there's more than one, list them and ask which. If there's none, ask where the file is.

Then say this plainly:
- This is free. No card, no trial, nothing to cancel.
- You'll click through two websites and answer a few prompts. You will not write code.
- **Ugly but live beats pretty but local.** We are not making it better today. We are making it real.
- If anything looks scary, stop and tell me what you see on screen. You can't break anything.

### 2. Make it a Git repo, in plain English
Explain the GitHub step before doing it, because "repository" is the word that scares people off:

> Git is a save system that keeps every version of your file. GitHub is a website that holds those saves online. Vercel — the free host — reads from GitHub and turns your file into a real web page. That's the whole chain. You're making a saved copy online, and then pointing a free host at it.

Then run it for them from inside their project folder:

```bash
cd ~/sites/<slug>
git init
git add .
git commit -m "First version"
```

If Git asks for a name and email the first time, tell them it's a one-time thing and set it:

```bash
git config --global user.name "Their Name"
git config --global user.email "their@email.com"
```

Now put it on GitHub. If they have the GitHub CLI, one command does everything:

```bash
gh repo create <slug> --public --source=. --push
```

If that command isn't found, walk them through the browser instead, one step at a time — never more than one instruction per message:
1. Go to github.com and sign in (make a free account if needed — email, username, password, that's it).
2. Click the **+** at the top right, then **New repository**.
3. Name it `<slug>`. Leave everything else alone. Click **Create repository**.
4. GitHub shows a box of commands. Tell them: "Copy nothing — I'll handle it. Just paste me the URL at the top of that page."
5. Take their URL and run the connect-and-push yourself.

### 3. Walk Vercel sign-in, one click at a time
Vercel is the free host. Give these one at a time, and wait for them to say done before the next:

1. Go to **vercel.com** and click **Sign Up**.
2. Choose **Continue with GitHub**. Use GitHub — it makes the rest automatic.
3. Approve the permission screen. Vercel is asking to read your repositories so it can publish them. Say yes.
4. Pick the **Hobby** plan when it asks. That's the free one. It will ask for your name; it will not ask for a card.
5. On your dashboard, click **Add New** then **Project**.
6. Find `<slug>` in the list and click **Import**.
7. Don't change any settings. Click **Deploy**.
8. Wait about 30 seconds. You'll get confetti and a link ending in `.vercel.app`.

Ask them to paste that link to you.

### 4. Fix the three things that actually go wrong
Check these before celebrating, because these are the three that trip up nearly every beginner:

**1. The page is blank, or shows a file list.**
Almost always the file isn't named `index.html`, or it's sitting inside an extra folder. Check with:
```bash
ls ~/sites/<slug>
```
If it's called `site.html` or `Untitled.html`, rename it to `index.html`. If it's one folder deeper, move it up. Then commit and push again — Vercel republishes automatically in seconds.

**2. The repo doesn't show up in Vercel's import list.**
Either it was created as private with limited access, or Vercel wasn't given permission to that repo. On the import screen there's an **Adjust GitHub App Permissions** link — click it and grant access to all repositories. Refresh.

**3. They pushed to GitHub and the live site didn't change.**
Two usual causes. Either the change was never committed — run `git status` and if it lists files in red, they weren't saved yet. Or their browser is showing the old cached page — tell them to open the link in a private window to check for real.

If they hit something not on this list, ask for one sentence describing exactly what they see on screen. Don't ask them to read logs.

### 5. Open it on your phone, then send it to a human
Two things, in this order, both today:

1. **Open the link on your phone.** Not the laptop. This is where you find the real problems — text too small, a button off the edge, an image pushing the layout sideways. Note what's wrong and fix it in a later session. Do not start fixing it now.
2. **Send the link to one real person.** A friend, your partner, someone in a group chat. Not for feedback, not for praise. The rep is the sending. Something you made now exists at an address anyone in the world can open, and you did it in an evening.

If they want a nicer address later, mention that a custom domain is about $12 a year and Vercel walks you through it — but not today.

### 6. Save the link to your list
Append to `~/my-links.md` (create it if it doesn't exist). Keep one line per shipped thing, newest at the bottom:

```markdown
# Things I've shipped

- 2026-07-30 — Treat Chase (game) — https://treat-chase.vercel.app — local: ~/games/treat-chase
```

Tell them the path and why it exists: in three months this file is the answer to "what have you actually built," and that list is worth more than any certificate.

## Output — save it
- `~/my-links.md` — a running list of every live thing they've shipped: date, name, live URL, and the local folder.
- The project folder is now a Git repo connected to GitHub and auto-publishing to Vercel on every push.

State the live URL and the path to `~/my-links.md`. Single next action: open it on their phone, then send the link to one person today.

## Example (input → output)
**Input:** "I made that snake game with my dog in it. How do I get it online so my sister can play it?"

**Output:**

Live at **https://treat-chase.vercel.app** in about 9 minutes. One snag along the way: the first deploy showed a blank page because the file was named `game.html` — renamed it to `index.html`, pushed, and it came back in 20 seconds.

Appended to `~/my-links.md`:
```markdown
- 2026-07-30 — Treat Chase (game) — https://treat-chase.vercel.app — local: ~/games/treat-chase
```

Next: open it on your phone, then text the link to your sister and ask for her score.

## Notes / edge cases
- The failure this prevents: building something good and never showing it to anyone, so it never becomes real and the momentum dies.
- Give one instruction per message during sign-up. A numbered list of eight steps pasted at once is where beginners get lost and quit.
- Never ask them to read an error log or a stack trace. Ask what they see on the screen, in one sentence, and translate it yourself.
- If they have no GitHub account, that's a two-minute signup, not a blocker. Say so before they assume it's a big deal.
- Every future change is: tell me what to fix, then `git add . && git commit -m "..." && git push` and the live link updates itself. Say this once so they know it gets easier.
- Hand off: **first-website**, **landing-page**, **link-in-bio**, **sales-page**, or **simple-game** if there's nothing built yet to deploy.
