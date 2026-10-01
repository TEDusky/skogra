# Main

Home. One scrollable scene. The clock is in the sky, the trail is the woods below. Intention, focus, confirm, placing an object, and the optional note all happen here. It is not a timer screen and a forest screen.

One duration: the session. There are no break timers.

## Session length

Default **25:00**. First launch, that is what the clock shows.

You change it when setting the intention, before the session starts. The field is prefilled with the current length (25 until you change it). Whatever you start with becomes the length the clock shows next time, until you change it again.

Idle, the clock is a readout, not an editor. Running, it only counts down.

A Settings screen for one number is not needed.

## Camera

**Idle**

- Vertical: pan between the timer (sky) and the woods.
- Horizontal: woods only. The sky does not pan sideways.
- An arrow shows that the scene continues: **down** on the timer view (woods below), **up** on the trail view (back to the clock). Hint only; the pan is still a scroll. Hidden while a session runs.

**Session running**

- No scrolling. Stay on the timer.

**After you finished something**

- Still on the timer: optional note (skip allowed). Then unlock. Camera eases down and along to the new object, just past the last one.

**After “not yet”**

- Stay on the timer, now idle. Keep the intention and tag if there were any (next prefill). No note, no object.

First launch: sky, clock, empty woods below.

## Elements

| Element                           | Why it is here                                                                                         | Tap                                                                                                                                | Next           |
| --------------------------------- | ------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------- | -------------- |
| Scene (sky + trail)               | The place that grows from finished work.                                                               | Idle: vertical pan timer↔woods. In woods: horizontal walk along the path. Running: gestures do nothing.                            | Stays on Main. |
| Timer (clock in the sky)          | The focus box. Idle: session length (default 25:00). Running: time left.                               | Display. Play / stop is in the center. Length is changed at set-intention, not here. Running: counts down only.                    | Stays on Main. |
| Play / stop (center of the clock) | Start a session. Stop early is allowed.                                                                | **Idle, play:** ask for intention (skip allowed) and session length. **Running, stop:** confirm. Clock at zero: same confirm, no tap. | Stays on Main. |
| Intention + tag                   | The receipt being attempted. Shown once a session is armed or running, and as prefill after “not yet.” | Running: display only. Arming: type or skip.                                                                                       | Stays on Main. |
| About (? , timer view)            | What this is, is not, why it exists, version. Chrome of the screen where the timer is visible, left or right — not on the clock, not a doorway. | Opens About. Idle only. Hidden while a session runs.                                               | About.         |
| List (icon, top right of trail)   | Read receipts when the forest is not enough. On the woods framing of Main, not on the sky.             | Opens List. Only when the timer is idle and you are looking at the trail. Hidden / unreachable while a session runs.               | List.          |
| Scroll arrow                      | Shows that the other half of the scene is there. Idle only.                                            | Timer view: points down. Trail view: points up. Not shown while a session runs. Does not start a session.                          | Stays on Main. |

Running, the only control is stop. About is a ? on the timer view (a side of that screen, not on the clock), idle only. The list icon is top right of the trail view; you cannot pan there while the timer is active.

## Moment: set intention

Before the clock runs. Same scene, over the sky.

**What would you like to get done?** One line. Optional project tag. Skip is allowed.

**Session length**, prefilled (25:00 until you change it). You can change the minutes here. Skip still uses that length — duration is not tied to writing a line.

| Tap                 | Result                                                                                    | Next           |
| ------------------- | ----------------------------------------------------------------------------------------- | -------------- |
| Start (with a line) | Timer runs for the chosen length. Label = that line. Tag = the tag if any. Length sticks. | Main, running. |
| Skip                | Timer runs for the chosen length. No intention. Length sticks.                            | Main, running. |
| Back / cancel       | Do not start. Length is not kept unless you started.                                      | Main, idle.    |

## Moment: confirm

Same moment whether the timer ended or you hit stop. Sheet over the scene. Still no scrolling until this is answered.

**If there was an intention: Did you finish it?**

| Tap                           | Result                                                       | Next                                             |
| ----------------------------- | ------------------------------------------------------------ | ------------------------------------------------ |
| **Yes**                       | Earn 1 object. Label = the intention. Tag = the session tag. | Optional note, still on the timer. |
| **Not yet**                   | No object. Keep intention and tag.                           | Main, idle, on the timer.                        |
| **I finished something else** | Type a line. Keep or change the tag. Earn 1 object.          | Optional note, still on the timer. |

**If the intention was skipped: Did you finish something?**

There is no “it”. **Yes** is not shown.

| Tap                      | Result                                           | Next                                             |
| ------------------------ | ------------------------------------------------ | ------------------------------------------------ |
| **Not yet**              | No object.                                       | Main, idle, on the timer. Blank intention.       |
| **I finished something** | Type a line. Set or skip the tag. Earn 1 object. | Optional note, still on the timer. |

## Moment: optional note

Only if you finished something. Same scene, still on the timer. Before the object appears. Not on “not yet.”

Free text. Skip is allowed. This is not a second label. Still no scrolling until this is answered.

| Tap         | Result                       | Next                                                      |
| ----------- | ---------------------------- | --------------------------------------------------------- |
| Save note   | Receipt includes the note.   | Object is placed. Camera eases to it. Main, idle, on the trail. |
| Skip / done | Receipt has no note.         | Object is placed. Camera eases to it. Main, idle, on the trail. |

The player does not choose the object or the spot. The app places it just past the last one, after this moment.
