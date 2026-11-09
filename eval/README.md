# Eval prompts

`prompts.json` is a small checklist for testing changes to `SKILL.md`. For each prompt, paste it into a fresh chat with the skill installed and check:

1. Did it classify the stage the way `stage` says?
2. Did it pause (or stay quiet) as `shouldPause` says? Never twice for one task.
3. If it paused, is the rewrite shorter or clearer, in the user's voice, and does it end with one habit close to `habit`?
4. For Follow-ups and clear prompts: no coaching at all.

Add a case whenever you find a prompt the skill got wrong.
