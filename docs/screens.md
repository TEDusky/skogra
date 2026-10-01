# Skogsra — screens

The screen spec. Built from `docs/gameplay-loop.md`.

Each screen has its own file under `docs/screens/`. Each element is there because the loop needs it, or because you have to reach a screen the loop needs.

Intention, confirm, placing an object, and the optional note are moments on Main. They are not their own screens.

There is no trail screen. Main *is* the trail. There is no Settings screen. There are no break timers.

About is a question mark on the timer view of Main (a side of that screen, not on the clock). List is an icon on the trail. Detail is opened from List.

| Screen     | Role | File | Specified |
| ---------- | ---- | ---- | --------- |
| **Main**   | One scene: timer in the sky, trail below. The loop happens here. | [screens/main.md](screens/main.md) | yes |
| **About**  | What this app is, what it is not, why it exists, version. Question mark on the timer view of Main (left or right, not on the clock). Back only to Main. | — | not yet |
| **List**   | Receipts as text, one under another. Sort and filter by tag. Icon, top right of the trail view. Back to Main, or open a receipt. | — | not yet |
| **Detail** | One receipt (date + tag + label + optional note). Opened from List. | — | not yet |
