# Skogsra — screens

The screen spec. Built from `docs/gameplay-loop.md`.

Each screen has its own file under `docs/screens/`. Each element is there because the loop needs it, or because you have to reach a screen the loop needs.

Intention, confirm, placing a light, and the optional note are moments on Main. They are not their own screens.

There is no trail screen. Main *is* the trail. There is no Settings screen. There are no break timers.

About is a question mark on the timer view of Main (a side of that screen, not on the clock). List is an icon on the trail. Detail is opened from List.

| Screen     | Role | File | Specified |
| ---------- | ---- | ---- | --------- |
| **Main**   | One scene: timer in the sky, trail below. The loop happens here. | [screens/main.md](screens/main.md) | yes |
| **About**  | What this app is, what it is not, why it exists, version. Question mark on the timer view of Main (left or right, not on the clock). Back only to Main. | [screens/about.md](screens/about.md) | yes |
| **List**   | Receipts as text, newest first, grouped by day. Tag filter shared with the trail. Icon, top right of the trail view. Back to Main, or open a receipt. | [screens/list.md](screens/list.md) | yes |
| **Detail** | One receipt (date + tag + label + optional note). Edit, delete, show on trail. Opened from List, or by tapping a light on the trail. | [screens/detail.md](screens/detail.md) | yes |

## Two views of the same work

The trail and List show the same receipts. The trail is newest last (end of the path); List is newest first. One tag filter is shared by both: on the trail, only matching lights stay lit; in List, only matching receipts are shown.
