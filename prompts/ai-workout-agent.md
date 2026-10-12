# AI Workout Agent — Setup Prompt

Build an AI trainer that writes your workout every morning, remembers what
you actually did, and adjusts when you give it feedback. No code. It's
three pages in Notion plus one daily scheduled task in your AI app.

- **Today's Workout**: the page you open at the gym. The AI writes it fresh
  each day; you log what you did and leave feedback at the bottom.
- **Workout History**: every past workout, archived automatically, newest
  at the top.
- **Workout Instructions**: the brain. Your goals, weekly plan, progression
  rules, and the step-by-step routine the daily task follows.

Every morning the scheduled task runs the same loop: **archive yesterday →
read the instructions and your feedback → write today's workout.**

---

## What you need

- **A Notion account.** The free plan works.
- **An AI app that can connect to Notion and run scheduled tasks**, such as
  Claude or ChatGPT. Scheduled tasks usually need a paid plan, so check
  yours.
- About 15–20 minutes. The AI interviews you, proposes a plan, builds the
  pages, and walks you through creating the daily task.

## How to use it

1. **Connect Notion to your AI app** before you start:
   - **Claude:** Settings → Connectors → Notion → Connect.
   - **ChatGPT:** Settings → Apps → Notion → Connect.
   - Other apps: look for "Connectors", "Apps" or "Integrations".
2. **Start a new chat** and paste the whole prompt below.
3. **Answer its questions.** It asks about your goals, schedule, equipment
   and injuries, then proposes a weekly plan. Push back on anything you
   don't like before you approve it.
4. **Follow along as it walks you through setting up the daily task**,
   including the one-time permission step. Don't skip that step; it's the
   one that makes the task run on its own.

---

## The prompt

Copy everything in the box below.

````text
Set up a self-updating AI workout trainer for me in Notion. It's three
Notion pages plus one daily scheduled task:

- "Today's Workout": the page I open at the gym. It's rewritten every day.
  I log what I actually did in it and leave feedback at the bottom.
- "Workout History": a running log of every past workout, newest at top.
- "Workout Instructions": the brain. My goals, weekly plan, the rules for
  writing workouts, and the step-by-step Daily Routine that the scheduled
  task follows.

The scheduled task holds no rules of its own. It only says "open Workout
Instructions and follow the Daily Routine." Everything lives in Notion, so
I can read and edit all of it, and if I switch AI apps later I just point
the new one at the same page.

Work through the steps below in order. Don't skip ahead, and don't create
anything in Notion until Step 4.

==========================================================================
STEP 1: CHECK NOTION ACCESS
==========================================================================

Confirm you can search, read, create and edit pages in my Notion
workspace. If you can't, stop. Tell me how to connect Notion in the app
we're using (Claude: Settings → Connectors → Notion. ChatGPT: Settings →
Apps → Notion. Otherwise look for Connectors, Apps or Integrations) and
wait for me to say it's done.

==========================================================================
STEP 2: INTERVIEW ME
==========================================================================

Ask me these in ONE message, numbered, so I can answer them all at once.
Tell me short answers and "not sure" are fine; you'll pick sensible
defaults.

1. Goals: what do I want from training? (Get stronger, build muscle, lose
   fat, endurance, general health, a sport or event.) Any specific target
   or date?
2. Experience: how long have I been training consistently? Any current
   numbers I know (e.g. "bench 135x5", "run a mile in 9:30")?
3. Schedule: how many days a week, which days, and how long per session?
4. Equipment: where do I train, and what's there? (Full gym, home gym,
   dumbbells only, bodyweight only, etc. If home, list what I have.)
   Anything a typical gym has that mine doesn't?
5. Injuries or limits: any injuries, pain, or medical conditions to work
   around?
6. Other activity: any cardio, sports, or classes to include or plan
   around?
7. Likes and dislikes: exercises I love, hate, or can't do?
8. Logistics: lbs or kg? My time zone, and what time I usually work out?

After I answer, ask at most one short round of follow-ups, and only if
something important is missing or contradictory. If I mention an injury
or medical condition, keep the plan conservative around it and suggest I
check with a doctor or physical therapist for anything serious, but still
build the plan.

==========================================================================
STEP 3: PROPOSE A PLAN AND GET MY APPROVAL
==========================================================================

In chat (not in Notion yet), propose:

- A one-sentence summary of the approach and why it fits my goal.
- A weekly schedule table: Day | Focus | Main exercises | Notes. Include
  rest days.
- The sets/reps scheme for main lifts vs. accessory exercises.
- How weights and reps will progress over time.
- How a typical session fits my time limit.

Build it from my answers. Match my days, session length and equipment
exactly. Balance the week (push, pull, legs, core, plus cardio if it's
relevant). Put the most time into what serves my main goal. For beginners,
favor a small set of simple, repeatable exercises over variety.

Ask me to approve it or request changes. Revise until I say it's good.

==========================================================================
STEP 4: BUILD THE NOTION PAGES
==========================================================================

Create a page called "Workouts" with the 🏋️ icon at the top level of my
workspace (or under a page I name). Add one line to it: "Open Today's
Workout each day. Log what you did in the Actual column and leave feedback
at the bottom." Inside it, create three pages: "Today's Workout",
"Workout History", and "Workout Instructions".

--- PAGE: Workout Instructions ---------------------------------------------

Fill this in from my answers and the plan I approved. Write it in plain
language that both I and a future AI can follow. Use exactly these
sections:

  (Callout at the top) "This page is the single source of truth for my
  workout system. The daily scheduled task reads it and follows the Daily
  Routine below. Edit anything here directly; the next run will follow
  your changes."

  ## About Me
  Goals, experience level, units (lbs or kg), time zone.

  ## Schedule
  Training days, session length, usual workout time.

  ## Equipment
  Available: (list)
  NOT available: (list; add to it whenever I say something is missing)

  ## Injuries & Constraints
  What to avoid or modify, and why. Or "None noted."

  ## Weekly Plan
  Table: Day | Focus | Main exercises | Accessories / cardio. Include rest
  days.

  ## Exercise Rules
  Sets/reps scheme, rest times, warm-up approach, exercise order, my likes
  and dislikes. Always use the same name for the same exercise so the
  history is easy to follow.

  ## Progression Rules
  (Use these defaults unless my answers call for something different.)
  - Every target is concrete: sets x reps @ weight (or bodyweight, time,
    or distance).
  - To set a target, find the last time I did that exercise in Workout
    History.
  - All sets done cleanly with no pain mentioned: step up a little. Add
    reps within the rep range first. Once I hit the top of the range on
    every set, add the smallest sensible weight (about 5 lb / 2.5 kg for
    upper body, 10 lb / 5 kg for lower body) and go back to the bottom
    of the range.
  - Missed reps, cut it short, or said it was too hard: keep the same
    target.
  - Missed the same target 2-3 sessions in a row: drop the weight about
    10% and build back up.
  - Pain mentioned: don't progress that exercise. Reduce it or swap in a
    pain-free alternative, and say why in the Target cell. Never program
    through pain.
  - Not logged (Actual left blank): there's no new data. Don't progress,
    don't count it as a failure, and repeat the last real targets.
  - No history for an exercise: give a conservative starting target and
    mark it "no history - log the weight you use."
  - Add short context to a Target when it helps, e.g. "3x5 @ 140 (135x5
    clean last Mon)."

  ## Daily Routine
  The scheduled task runs this once a day. Follow the steps in order.
  1. Work out today's date and weekday in my time zone.
  2. Open Today's Workout. If its heading already shows today's date,
     stop: today is already written.
  3. Archive. If Today's Workout has a past workout on it, copy ALL of
     it to the TOP of Workout History: the heading, every table, my
     Actual entries, Notes and Feedback, exactly as I wrote them. Don't
     summarize or tidy anything. Right under the heading, add a status
     line: "Status: Completed", "Status: Partial", or "Status: Not
     logged" (nothing entered). Put a divider between days. If Today's
     Workout is empty (the first run), skip this step.
  4. Read my feedback: the Feedback section, the Notes section, and
     anything I wrote in the Actual column.
     - One-off ("only have 30 min tomorrow", "skip legs this week"):
       apply it only for as long as it applies.
     - Lasting change ("my gym has no cable machine", "I want 4 days a
       week now", "more back work"): edit the matching section of THIS
       page, then add a dated line to the Change Log.
     - "Repeat that workout", or I skipped it and want it again: rewrite
       the same workout for today.
     - Unclear: make your best call for today and put one short question
       in the line under today's heading.
     Never delete or override something I wrote on this page unless my
     feedback clearly asks for it.
  5. Check recent history. Read only the most recent two weeks or so at
     the top of Workout History; it gets long, so don't read the whole
     page. Note my last result for each exercise you're about to program.
  6. Write today. Replace everything on Today's Workout with today's
     workout, following the Weekly Plan, Exercise Rules, Progression
     Rules, and the Today's Workout Format below. On a rest day, write a
     short rest-day page (optional light walk or mobility) so I can see
     the system ran.
  7. Double-check before finishing: equipment only from the Available
     list, nothing that conflicts with Injuries & Constraints, fits my
     session length, and every target is concrete.
  If Notion can't be reached or a page is missing, stop and report the
  problem. Never leave a half-written page.

  ## Today's Workout Format
  - Heading: "# Weekday — Mon D, YYYY — Focus"
    (e.g. "# Tuesday — Jan 6, 2026 — Lower Body")
  - One line under the heading for anything notable today: a PR attempt,
    a change made because of my feedback, or a question for me. Leave it
    out if there's nothing.
  - One section per part of the workout (e.g. Warm-up, Main Lift,
    Accessories, Core, Cardio). Each is a "## Section name" heading
    followed by a table with three columns: Exercise | Target | Actual.
    Leave Actual blank for me.
  - "## Notes": left empty for me.
  - "## Feedback": with the placeholder text "How did it go? Anything to
    change? (e.g. 'my gym has no cable machine', 'too long', 'more back
    work')"
  - Keep it lean. Only write notes about things that matter (a PR, a pain
    flag, a change from feedback). Don't narrate routine weight bumps.

  ## Change Log
  - (today's date): Initial setup.

--- PAGE: Workout History --------------------------------------------------

Just one line for now: "Past workouts, newest at the top. Each day is
archived here automatically before the new workout is written."

--- PAGE: Today's Workout --------------------------------------------------

Leave it empty except for one line: "Your first workout will appear here
after the daily task runs for the first time." Do NOT write a workout
here yourself. The first test run in Step 5 writes it. That proves the
whole loop works and triggers every permission prompt while I'm watching.

When the pages are built, send me the link to the Workouts page.

==========================================================================
STEP 5: WALK ME THROUGH SETTING UP THE DAILY TASK
==========================================================================

Tell me in a sentence that the scheduled task is what makes this run on
its own, and that I'll create it myself in my AI app while you walk me
through it. Then go one step at a time, waiting for me to confirm each one
before moving on.

A) Give me the exact task text to paste, in its own code block, with the
   real link to my Workout Instructions page filled in:

   Open my Notion page "Workout Instructions" (<link>) and carry out
   its "Daily Routine" section exactly. That page is the only source of
   rules; don't rely on memory of earlier runs or anything else. If you
   can't reach Notion or can't find that page, stop and report the
   problem instead of guessing.

B) Recommend a time: daily, at least an hour before my usual workout, in
   my time zone. Early morning (around 4-5 AM) works for most people.

C) Walk me through creating the task. Use the notes below for the app
   I'm on. Menus change, so if what I see doesn't match, adapt, or ask
   me to describe what's on my screen.
   - Claude (desktop app or claude.ai): confirm Notion is connected
     (Settings → Connectors). Click "Scheduled" in the left sidebar →
     "New task" → set it up manually. Name it "Daily Workout", paste the
     task text as the prompt, set the frequency to Daily at the chosen
     time, and save.
   - ChatGPT: confirm Notion is connected (Settings → Apps). Open
     "Scheduled" in the sidebar, or ask ChatGPT in a chat to "schedule a
     daily task", and create a daily recurring task with the task text
     as its instructions at the chosen time.
   - Any other app: find where it creates scheduled, recurring or
     automated tasks. Make sure that task is allowed to use the Notion
     connection, paste the task text, and set it to run daily.

D) The one-time permission step. Explain this clearly, because it's the
   step people miss: the first time the task touches Notion, the app will
   probably ask permission to read and edit my pages. If that happens at
   4 AM with nobody there to click "allow", the run just stalls and no
   workout appears. So:
   - Have me run the task once by hand right now, using "Run now" or the
     app's equivalent. If there's no such button, paste the task text
     into a new chat.
   - Tell me to approve every permission prompt, choosing "Always allow"
     (or the equivalent) when offered, so future runs don't stop to ask.
   - This run writes my first workout into Today's Workout.

E) Once I say it finished, re-read Today's Workout yourself and confirm a
   real workout is there and matches the plan. If it isn't, help me
   troubleshoot: is Notion enabled for the task, was a permission prompt
   declined or left unanswered, is the page link right, or is the run
   still going?

F) Finish with a short "how to use it" note:
   - Open Today's Workout each day and type what you actually did in the
     Actual column, in any format ("3x5 @ 135", "done", "skipped",
     "swapped for rows").
   - Leave feedback at the bottom in plain words. Lasting changes get
     written into Workout Instructions automatically.
   - You can edit Workout Instructions directly at any time.
   - Skipped days are fine. They're archived as "Not logged" and the plan
     picks up where you left off.
   - If a morning's workout ever doesn't show up, open the scheduled
     task's latest run in your AI app; it's usually waiting on a
     permission prompt.
````

---

## Setting up the daily task (reference)

The AI walks you through this at the end of setup. Here it is in one place
in case you want to do it yourself or redo it later.

**1. The task text.** The AI gives you a version with your page link filled
in. It looks like this:

```text
Open my Notion page "Workout Instructions" (<link to your page>) and carry
out its "Daily Routine" section exactly. That page is the only source of
rules; don't rely on memory of earlier runs or anything else. If you can't
reach Notion or can't find that page, stop and report the problem instead
of guessing.
```

That's the entire task. All the logic lives on your Notion page, so the
task never needs editing. If you switch AI apps, paste the same text into
the new one.

**2. Create a daily scheduled task.**

- **Claude:** Click **Scheduled** in the left sidebar → **New task** →
  set it up manually. Give it a name, paste the text above as the prompt,
  choose **Daily** and a time, and save.
- **ChatGPT:** Open **Scheduled** in the sidebar (or ask ChatGPT in a chat
  to "schedule a daily task") and create a daily recurring task with the
  text above as its instructions.
- **Anything else:** look for scheduled, recurring or automated tasks.
  Make sure the task can use your Notion connection.

Menus move around between versions. If yours look different, the idea is
the same: a task that runs daily, has Notion access, and uses the text
above as its prompt.

Pick a time at least an hour before you usually train. Early morning
(4–5 AM) works for most people.

**3. Run it once by hand and approve the permissions.** This is the step
people miss. The first time the task touches Notion, your AI app will ask
permission to read and edit your pages. If that prompt shows up at 4 AM
with no one there to approve it, the run stalls and you get no workout.
So click **Run now** (or your app's equivalent), approve every prompt, and
choose **Always allow** if it's offered. When the run finishes, your first
workout appears in Today's Workout. From then on it runs on its own.

## Troubleshooting

- **No workout this morning:** open the task's most recent run in your AI
  app. It's usually waiting on a permission prompt. Approve it and choose
  "Always allow" if you can.
- **It asks for approval every single day:** check the connection's
  settings in your AI app for an option to allow Notion edits without
  asking. Some apps or plans don't offer one, and on those the task can't
  run fully unattended.
- **It programmed equipment you don't have:** say so in the Feedback
  section ("my gym has no cable machine"). It adds that to the NOT
  available list in your instructions so it doesn't happen again.
- **You want to change the plan:** write it in Feedback ("switch to 4 days
  a week") or edit Workout Instructions directly. Either way, the next run
  uses it.

## Make it yours

Nothing here is specific to workouts. Swap the interview and the
Instructions page for meal planning, a study schedule, or a content
calendar. Anything where you want a daily plan that adjusts to what
actually happened works the same way: the three pages and the loop stay
the same.
