# Skill Starter

Turn a job you keep asking Claude to do into your own slash command.

The trigger is simple: **you've asked for the same kind of thing two or three times.** That's the moment to bottle it. This skill interviews you for the job, the steps, and the words you'd actually type to ask for it — then writes a working skill you can run forever. It's the one that turns you from someone who uses other people's skills into someone who makes their own.

## Install

1. Copy the `skill-starter` folder into your Claude Code skills directory:
   ```bash
   cp -r skill-starter ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/skill-starter`.

## How to use

No setup needed. Type `/skill-starter` and describe the job you keep repeating. It asks what goes in and what comes out, how you'd phrase the request in your own sloppy words, the steps you'd take by hand, and where the result should be saved. Then it writes a `SKILL.md` into `~/.claude/skills/<your-slug>/`.

Restart Claude Code and type `/<your-slug>`. If it doesn't show up, you didn't restart — skills only load when a session starts.
