# Free Skills

Free Claude Code skills for my YouTube audience.

Each skill lives in its own folder. Grab the one you want, drop it into your Claude Code skills directory, and start using it. That's the whole setup.

No API keys. No installs. No scripts to run. If you have Claude Code, these work.

> **Want to actually learn Claude Code?** Join the [Claude Code Club](https://www.skool.com/claudecodeclub) — learn Claude Code plus all my resources, for just $9.

## Start here

Run [`personalize`](./personalize) first. It asks you a few questions about your name, niche, offer, and audience, then saves the answers to `~/.claude/brand-profile.md`.

Every other skill in this pack reads that file. That's how they write in your voice, for your audience, without you re-explaining yourself every time. You only do this once.

## Skills

### Setup

| Skill | What it does |
| --- | --- |
| [`personalize`](./personalize) | Sets up your brand profile so every other skill writes in your voice. Run this first, once. |

### Get your offer right

| Skill | What it does |
| --- | --- |
| [`offer-builder`](./offer-builder) | Builds a Hormozi-style Grand Slam Offer using the Value Equation — stacked deliverables, a name, a guarantee, and a one-line pitch you can say out loud. |
| [`positioning-filter`](./positioning-filter) | Finds the one angle that makes you different, so you stop sounding like everyone else in your niche. Saves a positioning statement you can reuse. |
| [`pricing-calculator`](./pricing-calculator) | Prices your offer on the outcome the buyer gets, not on your hours. Gives you three tiers and the value story behind the number. |

### Get customers

| Skill | What it does |
| --- | --- |
| [`warm-outreach`](./warm-outreach) | Builds a ranked list of people who already know and trust you, plus a first message that opens a conversation instead of pitching a friend. |
| [`dm-writer`](./dm-writer) | Writes one short, human DM to one specific person for one specific reason. Sounds like you texting someone you respect. |
| [`first-customer-closer`](./first-customer-closer) | Turns "someone's interested and I don't know what to say" into a calm sales script using the CLOSER framework. Built for people who hate selling. |
| [`objection-handler`](./objection-handler) | Turns the pushback you actually hear ("too expensive", "no time", "let me think about it") into honest answers you can give without freezing. |

### Make content

| Skill | What it does |
| --- | --- |
| [`content-prompt`](./content-prompt) | Gives you one question worth answering on camera, plus five hooks and text overlays. For short-form you can film today. |
| [`daily-post-ideas`](./daily-post-ideas) | Five LinkedIn post ideas, one per category, each with a ready-to-paste hook line and an angle. |
| [`hooks`](./hooks) | YouTube hooks using the Kallaway desire framework — visual, spoken, and on-screen text, each one scored. |
| [`dissect`](./dissect) | Paste a post or hook that's performing and get back why it works, plus a brief for rebuilding the mechanism for your own audience. |

### Everything else

| Skill | What it does |
| --- | --- |
| [`meeting-notes`](./meeting-notes) | Turns any meeting transcript into a clean markdown summary with decisions and action items. Works with Fireflies, Otter, Granola, Zoom. |
| [`fable-goal`](./fable-goal) | Turns a rough, spoken-out-loud idea into one exceptional `/goal` prompt you can paste straight into a fresh Fable session. |

More skills get added here over time.

## A suggested order

If you're starting from zero and want a path instead of a menu:

1. `/personalize` — set up your profile
2. `/offer-builder` — build something worth selling
3. `/pricing-calculator` — put a real number on it
4. `/positioning-filter` — sharpen how you say it
5. `/warm-outreach` — find the first people to tell
6. `/dm-writer` — write the actual message
7. `/first-customer-closer` — have the conversation
8. `/objection-handler` — handle the pushback

Then use the content skills to keep the top of the funnel full.

## How to install a skill

A skill is just a folder with a `SKILL.md` inside. To install one:

1. Download the folder for the skill you want (see [Downloading a single folder](#downloading-a-single-folder) below).
2. Move it into your Claude Code skills directory:
   - **Personal (all projects):** `~/.claude/skills/`
   - **Project-only:** `.claude/skills/` inside the project
3. Restart Claude Code (or start a new session).
4. The skill is now live. Invoke it by typing `/` followed by the skill name, for example `/personalize`.

Your folder should end up looking like this:

```
~/.claude/skills/
└── personalize/
    └── SKILL.md
```

## Downloading a single folder

You don't have to clone the whole repo. A few easy ways to grab just one folder:

**Option A — clone once, copy what you want**

```bash
git clone https://github.com/duncan-buildroom/freeskills.git
cp -r freeskills/personalize ~/.claude/skills/
```

**Option B — install the whole pack at once**

```bash
git clone https://github.com/duncan-buildroom/freeskills.git
cd freeskills
for d in */; do cp -r "$d" ~/.claude/skills/; done
```

**Option C — download the whole repo as a ZIP**

Click the green **Code** button on the [repo page](https://github.com/duncan-buildroom/freeskills), choose **Download ZIP**, unzip it, and copy the folder you want into `~/.claude/skills/`.

## License

Free to use and modify. Made for builders.

---

**Want to actually learn Claude Code?** Join the [Claude Code Club](https://www.skool.com/claudecodeclub) — learn Claude Code plus all my resources, for just $9.
