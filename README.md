# Land · Water · Air

A fast-paced animal-sorting game for kids. An animal appears in the centre ring — send it to its home before the timer runs out.

Single self-contained HTML file. No build step, no dependencies, no network calls.

**Play now:** https://sonsycode26.github.io/Game/
**Source:** https://github.com/SonsyCode26/Game

## Play

Open the link above, or run it locally — clone the repo, or download `index.html` on its own, and open it in any modern browser. That's it.

```bash
git clone https://github.com/SonsyCode26/Game.git
```

## Modes

| Mode | Prompt | You pick |
| --- | --- | --- |
| **Classic** | A habitat ("Water") | The animal that lives there |
| **Advanced** | An animal (a shark) | The habitat it lives in |

## Rules

- Three lives. A wrong answer or an expired timer costs one.
- The timer frame empties as you go, and rounds get shorter the longer you last.
- New animals unlock as you win rounds — medium at 3, hard at 8, expert at 15.
- **Bonus animals** live in more than one habitat (a penguin is land *and* water, a duck is all three). Select every habitat that applies.

## Scoring

```
points = base + streak bonus + bonus-animal bonus

base          100–500, scaled by how much time was left
streak bonus  15 per consecutive correct answer, capped at 10
bonus animal  +75
```

High scores are tracked separately per mode.

## Controls

- Choosing **Classic** or **Advanced** on the first screen starts that round straight away
- Tap or click an answer
- Keys `1` `2` `3` select answers; Enter or Space replays the last mode
- Sound can be toggled from any screen

## Accessibility & display

- Black night theme by default; a daylight theme ships alongside it (`data-theme="light"`)
- Responsive from phone widths up to wide desktop
- Every animal comes with a fact shown after the round

## Look & feel

Pixel art end to end: pastel storybook sprites — cream / blush / mint clouds, lavender mountains, a snow-capped peak — sitting on a black night sky.

- **Palette:** ~20 pastel colours sampled from the reference landscape, used flat. No gradients, no colour blending, no rounded corners, no blurred shadows. The default theme is **night** — flat black background, pastel sprites, butter-yellow accents, and deliberately quiet borders so the outlines frame the game instead of competing with it. A full **daylight** theme is built from the same palette (with a hard-banded sky) and can be switched on with `<html data-theme="light">`.
- **Type:** Press Start 2P for titles, scores and prompts; Silkscreen for body copy and labels (long names like BUTTERFLY have to fit a third of a phone screen). Both are SIL Open Font Licensed, latin subsets inlined as base64.
- **Art:** every icon is pixel art from `assets/` — the three habitat illustrations plus 30 animal sprites in `assets/animals/`. Backgrounds are cut out by flood-filling from the border (so white eyes, bellies and highlights survive), downscaled to 96px, reduced to 24 colours and inlined as base64 PNGs. The land sprite doubles as the mountain in the play scene.
- **The scene** under the timer is a small landscape: a snow-capped peak planted in the grass, a pond, rocks, drifting clouds and twinkling sparkles, drawn as inline SVG sprites and masks so they re-tint with the theme.
- **The character** (`assets/character.png`) reacts to every correct answer — she runs to the mountain for land, wades into the pond for water, leaps for air, and stumbles when the answer is wrong. The animations move her sprite box, so its bottom edge is her feet.
- Every icon sits in an inset sprite window, so answers read as framed sprites. No emoji anywhere in the interface.

The roster is 26 animals plus 4 multi-habitat bonus animals — one per sprite in `assets/animals/`. Adding an animal means adding a sprite there and an entry in `ANIMALS`.

## Technical notes

Vanilla JavaScript, inline CSS, Web Audio API for sound effects. State lives in `localStorage` (high scores and the mute preference) — nothing leaves the browser. Fonts and images are embedded, so the single file still runs offline with no network calls.
