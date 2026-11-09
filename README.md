<p align="center">
  <img src="prompt-sensei-banner.png" alt="Prompt Sensei: stops costly prompts, teaches better ones. Spend check, stage-aware, nothing stored, open source." />
</p>

# prompt-sensei

A Claude skill that looks over your prompt before you spend anything on it, then teaches you one small habit to make the next one better.

It does three things:

1. **Spend check.** If a request is likely to burn lots of usage without getting finished well (clicking through an app by screenshot, a two-hour video in one pass, "regenerate until it looks right"), it pauses once and offers cheaper strategies.
2. **Sensei rewrite.** It suggests a better version of your prompt, shaped by what you are already building: your project instructions, files, skills, trackers and earlier decisions. Clearer, smaller to start, in the right order, and reusing what you already have.
3. **One habit.** Each rewrite ends with a single thing to practice, so you improve a little every time.

You pick: use the rewrite, run your original, or edit it. Your call always wins.

## Stage-aware, so it stays out of your way

It reads what you are doing before it judges anything.

| Stage | Example | What it asks for |
|---|---|---|
| Exploring | "why is this slow?" | Nothing. A rough question is fine. |
| Diagnosing | "it should do X but does Y" | The evidence: expected, actual, any error. |
| Building | "make / write / fix ..." | Goal, done-test, what to reuse, one boundary. |
| Verifying | "check this against ..." | What to check and the scope. |
| Reusable | "make me a template" | Inputs, output shape. |
| Follow-up | "ok do it" | Nothing. It stays quiet. |

## What the pause looks like

```
What I noticed (Building): whole-video pass through an editor by screenshots. High cost.
Better strategy: test the first 10 minutes; cuts before captions.

Sensei rewrite:
  "Using the transcript, list the cut-off sentences in the first 10 minutes..."

Why: captions get made once; a transcript costs far less than screenshots.
Habit to practice: start small. Try the first 10 minutes, then scale.

[ Use the rewrite ]  [ Run my original ]  [ Let me edit it ]
```

More in [examples/example-pauses.md](examples/example-pauses.md) and [examples/prompt-gallery.md](examples/prompt-gallery.md).

## It also catches secrets

If a prompt contains an API key, password, token or private link, it pauses first and suggests labeled placeholders. This outranks everything else.

## Commands

- `/prompt-sensei <your prompt>` returns the stage, what is missing, an improved version and one habit.
- `/prompt-sensei score <prompt>` gives a readiness label (Early, Developing, Good, Ready) and the one thing that would move it up.
- `/prompt-sensei` reviews your last message.
- `/prompt-sensei watch` adds a one-line tip after each reply for this chat. `/prompt-sensei stop` (or "quiet mode") silences it, and "sensei on" brings it back.
- `/prompt-sensei help` lists the commands.

## Install

**Claude (Cowork / claude.ai):** Settings, Capabilities, Skills, upload `prompt-sensei.skill`, or zip the `prompt-sensei` folder.

**Claude Code:**

```
mkdir -p ~/.claude/skills
cp -r prompt-sensei ~/.claude/skills/
```

Start a new session. It loads when a request matches, or type `/prompt-sensei`.

## Privacy

No files written, no history kept, nothing sent anywhere. It reads only what is already in your session, and looks at past chats only if you ask. The readiness label is a coaching signal, not a grade or a promise about the answer you will get.

## How it differs from other tools

- [usage-guard](https://github.com/shirley-xue-2025/usage-guard) watches your usage percentage with a background daemon and pauses near the limit. Prompt Sensei works earlier, on the prompt itself. They pair well.
- [Prompt-sensei by chengzhongwei](https://github.com/chengzhongwei/Prompt-sensei) is a local-first coach for Claude Code and Codex with hooks, scoring history and lookback reports. It inspired this project's stage-aware design and "one habit at a time". Use that one if you want long-term coaching stats in a coding agent; use this one if you want a spend and fit check for any Claude chat, Cowork or Claude Code session.
- Token-trimming skills shorten Claude's replies. Prompt Sensei changes the plan and the prompt.

## Limits

It is instructions, so it is judgment-based. It can't see your real usage meter or exact costs, and it only knows the context your session has already loaded. It pauses at most once per task.

## Testing changes

[eval/prompts.json](eval/prompts.json) is a short checklist of prompts and what the skill should do with each. Add a case when you find one it gets wrong.

## Contributing

Add a trap, a cheaper strategy, a habit or an example in `examples/` and open a pull request. See [docs/philosophy.md](docs/philosophy.md) for the principles and [CHANGELOG.md](CHANGELOG.md) for history.

## License

MIT
