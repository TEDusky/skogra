# Skogsra — tech

Kept as simple as possible. Add a library only when the plain way hurts.

## Look and feel come first

The app must be aesthetically pleasing and smooth. That is a requirement, not polish.

- Target: a steady 60 fps on a mid-range Android phone. Panning, the character walking, glows, and the clock pie all stay smooth.
- **Flame is the first choice, not a fixed one.** The first scene slice (woods, lights, character, camera) is also the test. If Flame cannot make it look and feel right, change the approach. For example: plain Flutter (`CustomPainter` + fragment shaders), Rive for the character and animated lights, or a different engine for the scene.
- Keep the scene behind one boundary (receipts in, taps out), so swapping how it is drawn does not touch the rest of the app.

## Platform

Android first. iOS later, so nothing Android-only in app logic; platform bits (notifications, exact alarms) stay behind one small service.

## Stack

- **Flutter + Flame.** Flame draws the scene (sky, clock, woods, lights). Flutter draws everything else (sheets, List, Detail, About).
- **State: cubits** (`flutter_bloc`). One cubit for the session phases (see `docs/main/main-timer.md`), one for receipts and the tag filter.
- **Storage: one JSON file** in the app's documents folder for receipts (`path_provider`). Hundreds of receipts is still a small file. No database.
- **Small settings in `shared_preferences`:** session length, prefill (intention + tag), the current session (phase, start time, length, intention, tag, earned label).
- **Notifications: `flutter_local_notifications`.** One scheduled notification for the end of a session.

## Receipt

| Field         | Type            | Notes                                              |
| ------------- | --------------- | -------------------------------------------------- |
| `id`          | string          | Random, made when the receipt is saved. Also seeds light kind and offset. |
| `finishedAt`  | date-time       | When the note step was saved or skipped. Local date groups by day. |
| `label`       | string          | Not empty.                                         |
| `tag`         | string or null  |                                                    |
| `note`        | string or null  |                                                    |
| `lengthMin`   | int             | Session length it was earned in.                   |
| `lightKind`   | string          | Picked at random when placed, by rarity. Never changes. |

Position is not stored. It comes from the order of receipts and the gaps between days (see `docs/main/main-trail.md`). The rare-light cooldown (how many more common / uncommon lights before the next rare) is kept in `shared_preferences`.

## Art sources

Budget: about **150 EUR**, for when code is not enough.

- **In code (free):** sky, clock, woods (generated silhouette layers), glows, flicker, fireflies, colour around lights.
- **SVG silhouettes (free, made in-house):** the light objects (lamp, lantern, tent, cabin, …). Replace with a pack if they look weak.
- **Bought or commissioned:** the character walk cycle, first. A pack (itch.io, CraftPix, Kenney) or a small commission. Every pack must allow commercial use.

## Later

- Export / import of the receipts file, before release.
- iOS.
