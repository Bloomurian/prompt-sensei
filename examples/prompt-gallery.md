# Prompt gallery

Copyable before and after prompts, one per stage. Each ends with the habit Prompt Sensei would suggest.

## Exploring: no change needed

**Before:** `why is my mix sounding muddy?`
**Sensei:** Strong exploring prompt. Ask it as is. If you want sharper answers next time, add the track or section.
**Habit:** Point at the material.

## Diagnosing

**Before:** `my newsletter keeps going to spam`
**After:**
```
My newsletter lands in spam for Gmail users but not Outlook. Sent from Mailchimp on my own domain, last 3 sends. I have not changed my sending address. List the 3 most likely causes in order, and the quickest check for each.
```
**Habit:** Show the evidence (what you expected, what happened).

## Building

**Before:** `make me a landing page for my course`
**After:**
```
Build one landing page for my course using my existing brand colors and the copy in 02_PROGRAMS/course-outline.md. Goal: visitors click "Join the waitlist". One file, no external dependencies, saved to 06_PROJECTS/site/. Show me the headline and section list first.
```
**Habit:** Define done.

## Verifying

**Before:** `check my invoice`
**After:**
```
Check this invoice against the signed quote. List every line where the amount, quantity or date differs, and anything missing. Do not change the file.
```
**Habit:** Set one boundary.

## Reusable

**Before:** `help me with weekly planning`
**After:**
```
Make me a 15-minute weekly review checklist: last week's wins, open tasks to carry over, three priorities for next week, and one thing to drop. Output as a checkbox list I can paste into my notes.
```
**Habit:** Ask for the shape.

## Spend trap: screenshots

**Before:** `Go through my 2-hour podcast video and fix every awkward cut.`
**After:**
```
Using the transcript with timestamps, list the awkward cuts in the first 10 minutes only. I will approve the list before we touch the rest.
```
**Habit:** Start small.

## Spend trap: hundreds of items

**Before:** `Rewrite all 300 product descriptions.`
**After:**
```
Rewrite 5 descriptions in the voice from my brand guide. I will approve the style, then apply it to the rest in one batch and save to a CSV.
```
**Habit:** Start small.

## Safety: secrets in a prompt

**Before:** `Why does this fail? curl -H "Authorization: sk-live-9f2..." https://api.example.com/orders`
**After:**
```
Why does this fail? curl -H "Authorization: [API_KEY]" https://api.example.com/orders — it returns 401 on the live key but works on the test key.
```
**Habit:** Protect private data. (And rotate that key.)
