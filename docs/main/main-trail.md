# Main — trail

What a light is, and the general logic of the path.

Values marked *(prototype)* are defaults to build with. Revisit after using the prototype.

## The path

Horizontal. A character walks along it and lights a light for every finished thing. The woods are dark silhouettes. A light colours the world within its radius. Between lights, it stays dark.

## The character

- Idle: stands just past the last light, at the end of the path.
- Placing: walks from where it stands to the new spot and lights it.
- Not controlled by the player. Tapping it does nothing. *(prototype)*
- Who it is: just a character. A small dark silhouette, like the boy in Limbo. No name, no story, no customization.

## A light

One receipt, drawn on the trail. Every receipt has exactly one light; no receipt, no light.

## Which kind of light

Picked at random when the light is placed, then stored with the receipt. It never changes after that, also when the receipt is edited.

| Light              | What it is                                              | Rarity          | Weight *(prototype)* |
| ------------------ | ------------------------------------------------------- | --------------- | -------------------- |
| Trail lamp         | Small pool of light marking the way.                    | Extremely common | 30                  |
| Hanging lantern    | Warm light swinging from a branch.                      | Common          | 15                   |
| Torch              | Flickering, adventurous, slightly wild.                 | Common          | 15                   |
| Campfire           | A welcoming place to stop and rest.                     | Uncommon        | 5                    |
| Candle in a jar    | Small, intimate light on a stump or rock.               | Uncommon        | 5                    |
| Swarm of fireflies | Drifting points of light around ferns or water.         | Uncommon        | 5                    |
| Glowing mushrooms  | Gentle fantasy light at the roots of trees.             | Uncommon        | 5                    |
| Luminous moss      | A faint glow tracing stones or fallen logs.             | Uncommon        | 5                    |
| Glowing tent       | Soft light through fabric; someone is resting inside.   | Rare            | 4                    |
| Shrine candles     | A mysterious woodland shrine or offering.               | Rare            | 4                    |
| Enchanted stone    | Ancient markings giving off a subtle glow.              | Rare            | 4                    |
| Cabin window       | A glimpse of shelter deeper in the woods.               | Extremely rare  | 3                    |

Weights add up to 100, so they read as percent.

**Rules for rare and extremely rare:**

- After a rare or extremely rare light, the next **5–10** lights (random, picked when it is placed) are common or uncommon only.
- The next rare or extremely rare after that cannot be the same kind as the last one.
- The rules apply when a light is placed. Deleting a receipt can bring two rares closer; that is fine.

## Order and position

- Lights are ordered by finished time, oldest first. Newest is at the end of the path.
- Position comes from the order and the gaps, not stored.
- A small offset (± 20 % of spacing, along the path) comes from the receipt id, so a light always lands in the same spot. *(prototype)*
- Deleting a receipt removes its light. The lights after it move back. Editing changes nothing.

## Spacing and gaps

- Spacing between lights on the same day: about a third of the screen width, so 2–3 lights are in view at once. *(prototype)*
- Days without a light make the gap longer: + 0.5 × spacing per empty day. *(prototype)*
- **The gap is capped at 3 × spacing**, however long you were away. A month off is a longer stretch of dark path, not a walk to the horizon. *(prototype)*
- Radius: under half the spacing, so dark gaps stay between lights. Each kind has its own radius within that. *(prototype)*
- Only lights near the screen are drawn.

## Placing a new light

After the note step (saved or skipped):

1. The tag filter clears.
2. Camera eases down to the character at the end of the trail (~1 s). *(prototype)*
3. The character walks to the new spot; the camera follows. A capped gap keeps this walk short (a few seconds at most). *(prototype)*
4. The character lights it. Colour spreads to its radius (~1 s). *(prototype)*
5. Main, idle, trail view.

## Camera on the trail

- Vertical: two stops, timer view and trail view. Pan between them; it snaps to the nearest. *(prototype)*
- Horizontal: trail view only, from the start of the path to just past the character.
- Panning down from the timer: the trail view is where you last left it. First time: the end of the trail.
- Locked while a session runs.

## Tag filter

- Shared with List. **All** by default.
- Matching lights look as usual. Others dim: no colour, no glow, just a faint shape.
- Dimmed lights can still be tapped and open Detail.

## Tapping a light

- Opens Detail for that receipt. Idle only.
- The tap area is at least 48 dp around the light, even when the light is smaller.

## Empty trail

First launch: dark woods, the character at the start of the path, no lights.

## Rendering *(prototype)*

Dark silhouette layers, plus a radial gradient glow for each light drawn on top with additive blending. Proper "colour comes back around a light" (a shader that desaturates outside light radii) comes with the art pass. The prototype draws 3–4 kinds (trail lamp, hanging lantern, campfire, cabin window); the rest come with the art pass.
