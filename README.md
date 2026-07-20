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
| **Advanced** | An animal (🦈) | The habitat it lives in |

## Rules

- Three lives. A wrong answer or an expired timer costs one.
- The timer ring tightens as you go, so rounds get shorter the longer you last.
- New animals unlock as you win rounds — medium at 3, hard at 8, expert at 15.
- **Bonus animals** live in more than one habitat (a frog is land *and* water, a duck is all three). Select every habitat that applies.

## Scoring

```
points = base + streak bonus + bonus-animal bonus

base          100–500, scaled by how much time was left
streak bonus  15 per consecutive correct answer, capped at 10
bonus animal  +75
```

High scores are tracked separately per mode.

## Controls

- Tap or click an answer
- Keys `1` `2` `3` select answers
- Sound can be toggled from any screen

## Accessibility & display

- Adapts to light and dark mode, following the system theme
- Responsive from phone widths up to wide desktop
- Every animal comes with a fact shown after the round

## Technical notes

Vanilla JavaScript, inline CSS, Web Audio API for sound effects. State lives in `localStorage` (high scores and the mute preference) — nothing leaves the browser.
