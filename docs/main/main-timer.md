# Main — timer

What this part of the scene is, and how it behaves.

Values marked *(prototype)* are defaults to build with. Revisit after using the prototype.

## Session phases

One session moves through these phases, in order. Only one session exists at a time.

| Phase       | What is on screen                                   | Leaves to                                   |
| ----------- | --------------------------------------------------- | ------------------------------------------- |
| **Idle**    | Clock with play. Scene pans.                        | Arming (tap play).                          |
| **Arming**  | Intention, tag, length over the sky.                | Running (start / skip), Idle (cancel).      |
| **Running** | Clock emptying, time left, intention + tag.         | Confirm (hold to stop, or clock at zero).   |
| **Confirm** | Did you finish it / something?                      | Note (earned), Idle (not yet).              |
| **Note**    | Optional note.                                      | Placing (save / skip).                      |
| **Placing** | Camera eases to the end of the trail, light comes on. | Idle, trail view.                         |

The phase is saved, with what it needs (start time, length, intention, tag, earned label). If the app is killed, it reopens in the same phase.

## Keeping time

- The clock does not tick in the background. A session stores its **start time** and **length**. Time left = start + length − now, worked out whenever the clock is shown.
- Reopening the app with time left: still Running.
- Reopening the app after time ran out: Confirm.
- Changing the device clock mid-session is not handled. *(prototype)*

## Length

- Whole minutes, **1–180**. Default **25**. *(prototype)*
- Set while arming. Kept only once a session starts. Next session prefills it.

## Stop

- Press and hold the clock for **1 second**. *(prototype)* The ring fills while you hold. Release early: nothing happens.
- A plain tap while running does nothing.
- Android back while running: the app goes to the background, the session keeps running.

## Clock at zero

- App open: short vibration, then Confirm. *(prototype)*
- App closed or in the background: a notification at the end time. Tapping it opens the app on Confirm.
- The notification is scheduled at start and cancelled on stop.
- Notification permission is asked the first time you tap play, not at first launch.
- Exact alarms: used if Android allows it. Otherwise inexact, which may be late by a few minutes. *(prototype)*

## Confirm and note

- An earned session becomes a receipt when the note step is saved or skipped. Its **finished time** is that moment. That is the date it is grouped under, also for a session that crossed midnight.
- No minimum session length. Stop after 10 seconds and say yes: you earn a light. Done is done.
