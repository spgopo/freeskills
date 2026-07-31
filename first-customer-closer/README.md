# First-Customer Closer

Someone's interested and you don't know what to say. This gives you a one-page sales script for that exact conversation.

Built for people who hate selling. The reframe it runs on: **a sales conversation is just helping someone get clear on whether this is right for them.** You ask honest questions, you listen, and if it fits you make it easy to say yes. If it doesn't fit, you say so. The script follows the CLOSER framework — clarify, label, overview, sell the outcome, explain concerns, reinforce.

## Install

1. Copy the `first-customer-closer` folder into your Claude Code skills directory:
   ```bash
   cp -r first-customer-closer ~/.claude/skills/
   ```
2. Restart Claude Code (or start a new session).
3. Invoke it by typing `/first-customer-closer`.

## How to use

Type `/first-customer-closer` and tell it who the prospect is, how they came to you, and whether it's a live call or a DM thread. It writes the six CLOSER stages with the actual words to say, a short list of questions to ask, the line that invites the sale, and a response for "let me think about it." The script saves to `~/first-customer-script.md`. Read it out loud once before the conversation.

It reads your brand profile at `~/.claude/brand-profile.md` to write in your voice. If you haven't set that up yet, run `/personalize` first.
