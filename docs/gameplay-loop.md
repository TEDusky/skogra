# Skogsra — gameplay loop

## What this is and what this is not

A focus timer that turns finished work into a sidescrolling forest. The timer and the trail are the same place: timer in the sky, woods below. The trail is a visual log of days you actually got something done. It is not a todo app nor project management.

Work lives wherever you already keep it (Trello, Jira, Keep, etc.). This app only asks what you meant to do, which project it belongs to, how long the focus box is, whether it got done, and then adds one object to the trail. If something was finished, you can add an optional note first. You can skip the note. Then the trail scrolls to the new object.

There are no break timers. Sitting is not a session.

## North star

Seeing that real effort has visible, lasting value. Each object on the trail is a receipt: date + project tag + a one-line description of what got finished + an optional note.

This place grew from what I completed.

**Reward completion, not sitting.**  
A finished 25 minutes with nothing done does not leave an object. A finished piece of work does.

## The only loop

One session can earn at most **one** object.

```
Set intention + tag + length → Focus → Confirm → Optional note (if earned) → Place object or skip → Repeat or stop
```

### 1. Set intention

Before the timer:

**What would you like to get done?**  
Free text. One line. Not a task database. Skipping is allowed; then the confirm step has to ask what (if anything) got done.

**Project tag** (MVP)  
Optional free-text tag (e.g. “flat”, “work”). Reuse previous tags; do not invent a folder of projects, tasks, or subtasks. The whole trail stays visible.

**Session length**  
Default **25:00**. Change it here, in the same moment as the intention. Skip still uses that length. Whatever you start with is the length next time, until you change it again.

### 2. Focus

A pomodoro-style timer. You can stop early. Done is done. The timer is a box to focus in, not the unit of reward. While it runs you stay on the clock; you do not walk the trail.

### 3. Confirm

Same moment whether the timer ended or you stopped it. The question depends on whether an intention was set.

**If there was an intention: Did you finish it?**

| Answer                        | Result                                                                 |
| ----------------------------- | ---------------------------------------------------------------------- |
| **Yes**                       | Earn 1 object. Label = the intention. Tag = the session tag.           |
| **Not yet**                   | No object. Same intention and tag, new timer — or stop.                |
| **I finished something else** | Type a line. Earn 1 object. Label = that line. Keep or change the tag. |

**If the intention was skipped: Did you finish something?**

There is no “it”. **Yes** is not shown.

| Answer                   | Result                                                                      |
| ------------------------ | --------------------------------------------------------------------------- |
| **Not yet**              | No object. New timer with a blank intention — or stop.                      |
| **I finished something** | Type a line. Earn 1 object. Label = that line. Set or skip the project tag. |

### 4. Optional note

Only if you finished something. Still on the timer. Before the object appears.

Free text. Skip is allowed. This is not a second label and not a task body. The label is still the one line from confirm. The note is extra — how it went, a detail, several things done in this session.

If you did not finish, there is no note. Stay on the timer.

### 5. Place object

Only after the note step (or skip). The app sets one object on the trail, just past the last one, in the same scene as the timer. The player does not choose the object or the spot. Which object appears is pseudorandom from the receipt (amount of finished tasks). The scene unlocks and scrolls to the end of the trail, to the new object.

Then start another session or leave.

## Cases that are not extra loops

**Several items in one timer**  
Still one session → at most one object. The trail logs stretches of work, not checkboxes. Several completed items can be summarized in the label, or spelled out in the optional note. One focus session still produces at most one object.

**Finished before the timer**  
Stop → same confirm → optional note if yes → place object. Do not invent a “queue reward” state. Then optionally set a new intention.

**Did not finish**  
No object. Continue with the same line and tag, or stop. The unfinished intention and tag can stay as the next prefill.

## Session in one glance

```
[ What are you working on? ]
[ Project tag (optional) ]
[ Session length (default 25:00) ]
            ↓
      [ Timer running ]
       (stop allowed; trail locked)
            ↓
  Intention set: Did you finish it?
    Yes / Not yet / Something else
  Intention skipped: Did you finish something?
    Not yet / I finished something
            ↓
     Optional note (if earned; skip allowed)
            ↓
     Object appears → trail (end of path)
            ↓
        Repeat or stop
```
