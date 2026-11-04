# Example pauses

Each example shows the prompt, then what Prompt Sensei says.

## 1. Editing a video by clicking through an app

**Prompt:** "Go through my 40-minute tutorial in my video editor and fix every cut-off sentence, then move all captions off my face."

**Sensei:**
*What I noticed:* Clicking an editor by screenshot over 40 minutes, then re-captioning. High cost.
*Better:* Test the first 10 minutes. Fix cuts first, captions last.

*Sensei rewrite:*
```
Using the transcript with timestamps, list every sentence that gets cut off in the first 10 minutes of the tutorial. I will extend those clips. After the cuts are final, regenerate captions once and set their position once, away from my face and the on-screen instrument. If it works, we repeat for the rest.
```
*Why:* Cuts before captions means captions are made once. A transcript is far cheaper than screenshots.

## 2. A build request that ignores your existing system

**Prompt:** "Make me a new page to track my launch tasks."

**Sensei:** (You already have a dashboard with a task list and a naming rule in your project instructions.)

*Sensei rewrite:*
```
Add a "Launch" project to my existing dashboard instead of a new page: tasks with owner, due date and status, using my usual file naming rules and saved in the projects folder. Show me the task list before you build anything.
```
*Why:* Reuses the tracker you already have, so nothing ends up in two places.

## 3. Same job for hundreds of items

**Prompt:** "Rewrite the description of all 300 products."

**Sensei rewrite:**
```
Rewrite 5 product descriptions in the voice from my brand guide. I will approve the style, then apply it to the rest in one batch with a template, saving to a CSV.
```

## 4. Regenerate until it looks right

**Prompt:** "Redo the slide deck until it looks perfect."

**Sensei rewrite:**
```
I will list the 3 things I want changed. Fix only those, one slide first, and show me before applying to the rest.
```

## 5. Overbuilt research

**Prompt:** "Do deep research with agents on the best microphone under $200."

**Sensei rewrite:**
```
Run three focused searches on the best microphones under $200 for home recording and give me a short comparison table with price, pros and cons.
```
