---
name: simple-game
description: Build a playable browser game in one sitting — one file, opens in any browser, works on a phone, no accounts or databases. Pick from a menu of classics tagged by how long they take, then make it yours with a reskin, one twist, your name on the title screen, and a saved high score. Use when the user says "/simple-game", "build me a game", "I want to make a game", "make a browser game", "can we build snake", "build a game I can send to my friends", "something fun to build", "I don't know what to build first", "make a game with Claude", or "build a game my kid can play".
---

# Simple Game — the best first thing you'll ever build

A game is the best first build, and not because it's easy. It's the best because you cannot lie to yourself about whether it works. Websites get a shrug. Games get played. And a game is one file with no login, no database, and nothing to set up — so the only thing between you and something real is describing it well.

## Setup
None. This skill works out of the box.

## Steps

### 1. Say why a game first
Open with this, short, in your own words:

- **It either runs or it doesn't.** No wondering if it's good. You press a key, the thing moves or it doesn't. That feedback loop teaches you more in one night than a week of reading.
- **People actually play games.** Send someone your website and they say "nice." Send them a game and they play it, then send you their score. That reaction is the thing that keeps a beginner building.
- **It's one self-contained file.** No database, no accounts, no payments, no server. Everything lives in a single `index.html` you can email to someone.

Then: "Pick one from this list, or tell me a game you loved and we'll build that."

### 2. Offer the menu
Show about eight, with honest time tags. Tell them the time is for the version that works, not the version that's polished.

**15 minutes**
- **Clicker** — click the thing, number goes up, buy upgrades. Simplest possible loop, and weirdly addictive.
- **Memory match** — flip cards, find pairs. Great one to reskin with your own images.
- **Whack-a-mole** — things pop up, you tap them, timer runs down. Works great on a phone.

**1 hour**
- **Snake** — grow, don't hit yourself. The classic first game for a reason.
- **Breakout** — bounce a ball, break bricks. Teaches you what "collision" means without you learning the word.
- **Flappy-style tapper** — one input, endless, brutally hard. Very shareable.

**One evening**
- **Platformer (one level)** — run, jump, reach the flag. Jumping that feels right takes iteration; that's the lesson.
- **Tower defense (one map, three waves)** — place things, watch them fight. Biggest build here; do this second, not first.

If they name a game not on the list, take it, and say honestly which bucket it lands in. If they pick "one evening" and it's their very first build, say plainly that a 1-hour one finished tonight beats an evening one abandoned at 60%.

### 3. Write the 4-section game spec
Do not start building from a one-line request. Fill this out with them first — it takes two minutes and saves an hour. Four sections, and the wording of each matters.

**1. CONTAINER**
> One self-contained `index.html`. No build tools, no external JavaScript libraries. Google Fonts only — one display font, one body font. One accent color plus neutrals, never the purple-to-blue gradient. Fixed play area, centered, that fits on a phone screen without scrolling. Works with touch and with keyboard.

**2. GAMEPLAY — one rule per bullet**
This is where beginners go vague and get a mess. Every single bullet is one rule, stated flatly. No paragraphs. Example for Snake:
> - The snake moves one square every 120ms in the direction it's facing.
> - Arrow keys and swipes change direction. It cannot reverse into itself.
> - Eating an apple grows the snake by one square and adds 1 point.
> - Hitting a wall or its own body ends the game.
> - A new apple appears in a random empty square.

Ten to fifteen bullets like that is a complete game. Write them together, read them back, and ask: "Is any bullet doing two things?" Split it if so.

**3. UI — placement only, no styling talk**
> Score top-left. High score top-right. A start screen with the title and "Press space or tap to play." A game-over panel with the score, the high score, and a restart button. Nothing else on screen.

**4. THE KICKER**
Always end the spec with this line, exactly:
> Show me a live preview when it runs.

That one sentence is the difference between guessing and seeing.

For sound, if they want it: **"Web Audio API, no external files."** Simple beeps generated in the browser — nothing to download, nothing to break. For anything saved between sessions: **"save to localStorage."**

### 4. Build it, then play it
Build the game from the spec. Save to `~/games/<slug>/index.html`. Create the folder.

Open it:

```bash
open ~/games/<slug>/index.html
```

Then: "Play it. Don't be nice about it. What felt wrong?"

Run the loop in plain English, 5-10 rounds. Game feel is almost entirely iteration. Real notes sound like:
- "It's too fast to react to."
- "The jump feels floaty."
- "I keep dying instantly and I don't know why."
- "Nothing tells me I scored."

Describe the symptom, never touch the code. Every couple of rounds, offer to commit it as a checkpoint so a bad idea can't cost them the working version.

### 5. The "make it yours" pass
A working clone is a tutorial. A working clone with your fingerprints on it is a thing you made. Do all five of these:

- **Reskin it.** Change the subject to something from their actual life. Snake becomes a dachshund chasing treats. Breakout becomes emails you're deleting. Whack-a-mole becomes your inbox at 9am. This one change makes people forward it.
- **One twist mechanic.** Exactly one. A power-up, a reverse-controls moment, a square that speeds you up, a mode that flips gravity every 10 seconds. One twist makes it theirs. Two makes it confusing.
- **Your name on the title screen.** "SNAKE — by Maya." Small, but this is the point of the whole exercise.
- **High score saved to localStorage.** So the number is still there tomorrow. This is what turns a demo into a game.
- **A share button.** Copies a line to the clipboard: "I scored 47 in Treat Chase. Beat it: <url>." Fill the URL in after deploying.

### 6. Save the notes and hand off
Write `~/games/<slug>/NOTES.md` with the spec bullets, the twist, and one line for next time.

Close with: "Run **deploy-it** to get a real link, then send it to three people tonight and ask for their score. Ugly but live beats pretty but sitting in a folder."

## Output — save it
- `~/games/<slug>/index.html` — the playable game, one file, phone and keyboard.
- `~/games/<slug>/NOTES.md` — the gameplay rules, the twist, and the next step.

State both paths. Single next action: run **deploy-it**, then send it to three people and ask for their score.

## Example (input → output)
**Input:** "I want to build a game but I have no idea what. Maybe something with my dog in it."

**Output (Snake, reskinned, saved to `~/games/treat-chase/index.html`):**

Title screen: **TREAT CHASE — by Maya.** Press space or tap to play.

The spec that built it, in `NOTES.md`:
- The dachshund moves one square every 120ms in the direction it's facing.
- Arrow keys and swipes change direction. It cannot reverse into itself.
- Eating a treat grows it by one square and adds 1 point.
- Every 5th treat is a golden treat worth 3 points and it vanishes after 4 seconds. *(the twist)*
- Hitting a wall or its own body ends the game.
- High score saved to localStorage.
- Sound: a short beep on eat, a lower one on death. Web Audio API, no external files.

Game over panel: score, best-ever, restart button, and a **Copy my score** button.

## Notes / edge cases
- The failure this prevents: a beginner's first build being something with no clear win state, so they can't tell if it worked and lose momentum. A game tells you immediately.
- If their idea needs multiplayer, accounts, or saved profiles across devices, say plainly that's a server build and not tonight. Offer the single-player version now and note the rest in `NOTES.md`.
- If a rule bullet is doing two things, split it before building. Vague bullets are where games go wrong, not the code.
- If they get stuck on game feel, change one number at a time — speed, or gravity, or size. Changing three at once means you learn nothing.
- Hand off: **deploy-it** to publish and get the share URL. **first-website** if they want a page around the game. **link-in-bio** if they want the game as one of their public links.
