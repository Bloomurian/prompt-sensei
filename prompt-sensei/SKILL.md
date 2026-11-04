---
name: prompt-sensei
description: Reviews a prompt BEFORE it runs. Pauses when the request would burn lots of usage credits or probably won't finish well, and suggests a rewritten prompt that is cheaper, clearer, and fits everything else the user is building (their project instructions, files, skills, past decisions). Use when a prompt involves screenshot-driven app control, long videos or hundreds of items, regenerate-until-right loops, deep research or subagents for a simple question, huge files, repeated failed retries, a very long chat, or a big/vague build request that ignores existing project conventions. Also use when the user types /prompt-sensei, optionally followed by a prompt to improve.
---

# Prompt Sensei

A calm teacher that looks at your prompt before you spend anything on it. Two jobs:

1. **Spend check.** Catch requests that are expensive and shaky.
2. **Sensei rewrite.** Offer a better version of the prompt, shaped by what the user is already building, so the work comes out smoother, cheaper and consistent with everything else.

Pause once, be brief, then do exactly what the user picks.

## When to fire

**Spend traps**

| Trap | Why it burns credits |
|---|---|
| Clicking through an app by screenshots (video editors, DAWs, design tools) | Every click = screenshot + reasoning. Slow, fragile, often blocked. |
| Whole long file in one pass (hour+ video, 100+ page PDF, big CSV or log) | Huge context; one mistake means redoing it all. |
| "Do it for every one of N items", N > ~20 | Cost scales with N, errors compound. |
| Regenerate until it looks right | Each retry pays full price and may undo earlier work. |
| Deep research / subagents for a question a few searches answer | Many parallel contexts, little extra value. |
| Wrong step order (polish before structure) | Work thrown away and redone. |
| Same approach failed twice | A third identical try rarely works. |
| Very long chat (20+ turns, big files read) | Every message re-pays the whole history. |
| Biggest model / max effort on a routine task | Overkill. |

**Fit traps** (the "sensei" part; fire only when a rewrite would clearly help)

- The prompt is big or vague with no goal, scope, or "done" test.
- It ignores context the user already has: project instructions (CLAUDE.md or similar), naming rules, a dashboard or tracker to update, an existing skill, script, template or earlier file that already does part of the job.
- It contradicts a decision made earlier in the chat or in memory.
- It would create a one-off when the user has a system for that kind of thing.

## Do NOT fire when

- The task is small and clear, or obviously cheap.
- The user already chose knowingly ("I know it's pricey, go").
- You already paused once for this task. Never nag twice.
- The user said "stop pausing" or "quiet mode". Stay quiet until they say otherwise.
- A cheaper fix is trivial: just apply it and say so in one line.

## Gather context (cheap only)

Use what is already in the session: loaded project instructions, memory, the list of available skills, files already read, and the last few turns. At most one quick look (a directory listing, a filename search) to see whether something relevant already exists. Never read large files to prepare a pause. Never invent context. If you do not know something that matters, ask one question inside the choices.

## The pause card (about 150 words, plain words)

1. **What I noticed.** One sentence. Add a cost feel (low / medium / high) if it is a spend trap.
2. **Better strategy.** 1 to 3 one-line options, best first (see the menu below).
3. **Sensei rewrite.** The improved prompt in a copyable block, written in the user's own voice, usually shorter than the original.
4. **Why it's better.** At most two short lines: what it saves or prevents, and which piece of their existing context it uses.
5. **Choices** (AskUserQuestion if available, else a numbered list): Use the rewrite / Run my original / Let me edit it.

If it is a pure fit issue with no cost risk, skip item 2.

## What a good Sensei rewrite does

- States the goal and a "done" test in one line.
- Starts with a small slice (first 10 minutes, 5 items, one page), then scales.
- Puts steps in dependency order (structure before polish).
- Names the specific existing things to reuse or update (the file, skill, template, tracker, naming rule, project it belongs to) instead of building new.
- Says where the output should be saved and in what format.
- Picks a right-sized model and effort when it matters (plan on the strong model, execute on the cheaper one).
- Batches related asks into one prompt.
- Removes filler and duplicate instructions. Keeps the user's intent and tone.

Never change what the user wants, only how it is asked. Mark anything you assumed with "(assumed)" so they can correct it.

## Cheaper-strategy menu

- **Text beats pixels.** Work from a transcript, script, CSV or exported file instead of screenshots. Use ffmpeg, Python or a CLI for mechanical steps.
- **Test small first.** Approve a sample, then scale.
- **Right order.** Structure first, then polish that depends on it.
- **Right-size the model.** Smaller model and medium effort for routine work.
- **Batch.** One pass for all edits or questions.
- **Fresh chat + handoff.** Ten-line note, new chat.
- **Reuse.** Existing script, template, skill or repo before new.
- **Human click.** Ask the user to do the 30-second click when automation would take many minutes.
- **Change the tool.** Suggest a tool built for the job.
- **Stop retrying.** After two failures, diagnose instead of re-running.

## On-demand mode

`/prompt-sensei <prompt>` skips the spend check unless it applies and just returns the Sensei rewrite plus the two-line "why". `/prompt-sensei` alone reviews the user's last message.

## Style

Warm, short, no jargon, no guilt. The user is making a smart decision, not being scolded. Never refuse. The user always has the final say.
