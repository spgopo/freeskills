# Prompt Fixer

Paste the prompt that gave you bad output. Get back why it failed and the rewritten prompt to run instead.

When output is wrong, beginners blame the model. It's almost always **a thin prompt, not a bad model.** This skill checks seven usual causes — too vague, three asks in one, no constraints, no format, no done-when, missing context Claude couldn't know, and asking for code instead of an outcome — names the one that did the most damage, and hands you a fixed version you can run right now.

## Install

1. Copy the `prompt-fixer` folder into your Claude Code skills directory:
   ```bash
   cp -r prompt-fixer ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/prompt-fixer`.

## How to use

No setup needed. Type `/prompt-fixer` and paste the prompt you used. If you still have what came back, paste that too — it makes the diagnosis sharper. Then say in one sentence what you actually wanted.

You get the cause in plain English, the rewritten prompt in a copy-ready block, and a short note on what changed and why. It saves to `~/briefs/fixed-<name>.md`. Run the fixed prompt in a **fresh** session — reusing the old conversation drags the wrong answer along with it.
