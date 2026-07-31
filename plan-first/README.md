# Plan First

Get a written plan you approve before Claude touches a single file.

Building too big is the number one thing that kills a beginner project. You describe the whole dream, the build starts on the whole dream, and four nights later nothing works. This skill does the opposite: it finds the **one job** your build has to do, cuts everything else onto a "later" list, and puts the moves in an order you can actually finish in your stolen hours.

## Install

1. Copy the `plan-first` folder into your Claude Code skills directory:
   ```bash
   cp -r plan-first ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/plan-first`.

## How to use

No setup needed. Type `/plan-first` and describe what you want to build, however big and rambling. It reads the idea back to you, makes you name the one job, then cuts hard — you'll see exactly what's in v1, what's waiting, and why each cut was made.

You get a file at `~/plans/<project>-plan.md` with your v1 scope, your later list, the moves in order, a checkable definition of done, and one first move small enough to start tonight. Nothing gets built until you say go.
