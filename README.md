# prompt-sensei

A Claude skill that looks over your prompt before you spend anything on it.

It does two things:

1. **Spend check.** If a request is likely to burn lots of usage without getting finished well (clicking through an app by screenshot, a two-hour video in one pass, "regenerate until it looks right"), it pauses once and offers cheaper strategies.
2. **Sensei rewrite.** It suggests a better version of your prompt, shaped by what you are already building: your project instructions, files, skills, trackers and earlier decisions. The rewrite is clearer, smaller to start, in the right order, and reuses what you already have so new work fits the rest.

You pick: use the rewrite, run your original, or edit it. Your call always wins.

## What the pause looks like

```
What I noticed: whole-video pass through an editor by screenshots. High cost.
Better strategy: test the first 10 minutes; cuts before captions.

Sensei rewrite:
  "Using the transcript, list the cut-off sentences in the first 10 minutes..."

Why: captions get made once; a transcript costs far less than screenshots.

[ Use the rewrite ]  [ Run my original ]  [ Let me edit it ]
```

More in [examples/example-pauses.md](examples/example-pauses.md).

## It also fires on "fit" problems

Even with no cost risk, it speaks up when a prompt is big and vague, ignores your project conventions, contradicts an earlier decision, or builds a one-off when you already have a system for it.

## Commands

- `/prompt-sensei <your prompt>` returns an improved version right away.
- `/prompt-sensei` reviews your last message.
- Say "quiet mode" to silence it, and "sensei on" to bring it back.

## Install

**Claude (Cowork / claude.ai):** Settings, Capabilities, Skills, upload `prompt-sensei.skill`, or zip the `prompt-sensei` folder.

**Claude Code:**

```
mkdir -p ~/.claude/skills
cp -r prompt-sensei ~/.claude/skills/
```

Start a new session. It loads when a request matches, or type `/prompt-sensei`.

## How it differs from other tools

- [usage-guard](https://github.com/shirley-xue-2025/usage-guard) watches your usage percentage with a background daemon and pauses near the limit. Prompt Sensei works earlier, on the prompt itself. They pair well.
- Token-trimming skills shorten Claude's replies. Prompt Sensei changes the plan and the prompt.

## Limits

It is instructions, so it is judgment-based. It can't see your real usage meter or exact costs, and it only knows the context your session has already loaded. It pauses at most once per task.

## Contributing

Add a trap, a cheaper strategy, or an example in `examples/` and open a pull request.

## License

MIT
