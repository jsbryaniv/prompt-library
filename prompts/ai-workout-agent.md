# AI Workout Agent — Setup Prompt

Paste this into an AI assistant that has access to your Notion workspace
(e.g. Claude with the Notion integration connected) and can run on a daily
schedule. It will set up a self-updating workout system: three Notion
pages plus a daily job that keeps them in sync.

This isn't limited to workouts — swap the specifics below for meal
planning, a study schedule, or anything else you want to run on autopilot
with daily feedback.

---

## The prompt

```
Set up a self-updating workout tracker for me in Notion, made of three pages:

1. "Today's Workout" — the page I open every day at the gym. Lay it out in
sections (e.g. by muscle group), each as a table with three columns:
exercise, target reps, and actual (which I'll fill in as I go). Below the
tables, include a notes area, and at the very bottom a "Feedback" section
where I can leave plain-language notes about how the workout went or what
I'd change (e.g. "my gym doesn't have cable machines" or "shift focus to
more back work").

2. "History" — a running log. Each day, archive the previous day's
"Today's Workout" page into this one (exercises, targets, and what I
actually did) before writing a new plan.

3. "Instructions" — the brain of the system. A plain-language page
describing my goals, my weekly split, and the rules for writing a
workout (e.g. how to decide when to increase weight or reps). This page
should be editable by me directly, and you should update it yourself
whenever my feedback implies a change (e.g. if I say a gym doesn't have
certain equipment, update the Instructions so future workouts don't
include it).

Every day, run this sequence:
1. Archive yesterday's "Today's Workout" into "History."
2. Read "Instructions," including my latest feedback. If my feedback
implies the instructions should change, update them.
3. Write a new "Today's Workout" page based on the (possibly updated)
Instructions.

Set this up to run once a day on a schedule, timed so the new workout is
ready before I'd typically head to the gym. The scheduled job itself
should just point at the "Instructions" page rather than storing any
logic directly — if I switch AI platforms later, I should be able to
point a new one at the same Notion pages with nothing else to change.

Start by asking me for my current goals, weekly split, and any equipment
constraints, so you have enough to write the first version of the
Instructions page.
```

---

## Before you run it

- You'll need an AI assistant with Notion access and the ability to run
  on a recurring schedule (e.g. Claude with a scheduled task, or an
  equivalent on another platform).
- Run the job once by hand after setup — most platforms will ask for
  one-time permission to access your Notion pages, and it won't run
  unattended overnight until you've approved that.
