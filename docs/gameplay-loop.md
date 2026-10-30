# Skogsra — gameplay loop

## What this is and what this is not

A focus timer that turns finished work into light in a dark, sidescrolling forest. The timer and the trail are the same place: timer in the sky, woods below. The trail is a visual log of days you actually got something done. It is not a todo app nor project management.

Work lives wherever you already keep it (Trello, Jira, Keep, etc.). This app only asks what you meant to do, which project it belongs to, how long the focus box is, whether it got done, and then adds one light to the trail. If something was finished, you can add an optional note first. You can skip the note. Then the trail scrolls to the new light.

There are no break timers. Sitting is not a session.

## North star

Seeing that real effort has visible, lasting value. Each light on the trail is a receipt: date + project tag + a one-line description of what got finished + an optional note.

This place grew from what I completed. The woods are dark until you finish something; every light brings colour back to the world around it.

**Reward completion, not sitting.**  
A finished 25 minutes with nothing done does not leave a light. A finished piece of work does.

## The only loop

One session can earn at most **one** light.

```
Set intention + tag + length → Focus → Confirm → Optional note (if earned) → Place light or skip → Repeat or stop
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
| **Yes**                       | Earn 1 light. Label = the intention. Tag = the session tag.           |
| **Not yet**                   | No light. Same intention and tag, new timer — or stop.                |
| **I finished something else** | Type a line. Earn 1 light. Label = that line. Keep or change the tag. |

**If the intention was skipped: Did you finish something?**

There is no “it”. **Yes** is not shown.

| Answer                   | Result                                                                      |
| ------------------------ | --------------------------------------------------------------------------- |
| **Not yet**              | No light. New timer with a blank intention — or stop.                      |
| **I finished something** | Type a line. Earn 1 light. Label = that line. Set or skip the project tag. |

### 4. Optional note

Only if you finished something. Still on the timer. Before the light appears.

Free text. Skip is allowed. This is not a second label and not a task body. The label is still the one line from confirm. The note is extra — how it went, a detail, several things done in this session.

If you did not finish, there is no note. Stay on the timer.

### 5. Place light

Only after the note step (or skip). The app sets one light on the trail, just past the last one, in the same scene as the timer. The player does not choose the light or the spot. A character walks along the path to the spot and lights it; the light colours the woods around it. Which kind of light appears (trail lamp, lantern, campfire, … cabin window) is random, by rarity — exact rules in `docs/main/main-trail.md`. The scene unlocks and scrolls to the end of the trail, to the new light.

## Art direction

Alto's Adventure colour palette, Hollow Knight-style layered silhouettes, on a horizontal plane.

- **The world is dark.** Woods are flat silhouette layers with parallax. Unlit, they are near-monochrome.
- **A character walks the path** and lights each new light. It waits at the end of the trail. A small Limbo-like silhouette: no name, no story, no customization.
- **Lights are the reward.** Each light colours the world within its radius. The radius is limited, so dark gaps stay between lights and the trail still reads as a string of lights after hundreds of them.
- **The sky** is an Alto-style gradient. It holds the clock.
- **Cheap on purpose.** Flat shapes and gradients, no hand-painted detail. Take the layering from Hollow Knight, not its drawing.
- **First launch** is a dark, empty woods under the sky.

### Clock

Reference: `art/reference/clock-idle.png`, `art/reference/clock-running.png`. Flat, white on the sky colour, no texture. It reads as a sun or moon in the sky.

- **Shape.** A white ring, with short tick marks around it like rays.
- **Idle.** A play triangle inside the ring. The session length is shown below it in small type.
- **Running.** The inside of the ring is a white disc that empties clockwise like a pie, from 12 o'clock, as time passes. Time left is shown below in small digits, with the intention and tag above them.
- **Sky.** Idle and running use different sky colours (the reference goes from light periwinkle to dark slate). In our sky this could be dusk falling while you focus.

Taken from the reference: the ring, ticks, pie, and small type. Left out: pause, mode switching (pomodoro / break), and the session dots. There are no breaks and no pause. Stop is press and hold (the ring fills while you hold), as cancel is in the reference, and goes to confirm.

Then start another session or leave.

## Cases that are not extra loops

**Several items in one timer**  
Still one session → at most one light. The trail logs stretches of work, not checkboxes. Several completed items can be summarized in the label, or spelled out in the optional note. One focus session still produces at most one light.

**Finished before the timer**  
Stop → same confirm → optional note if yes → place light. Do not invent a “queue reward” state. Then optionally set a new intention.

**Did not finish**  
No light. Continue with the same line and tag, or stop. The unfinished intention and tag can stay as the next prefill.

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
     Light appears → trail (end of path)
            ↓
        Repeat or stop
```
