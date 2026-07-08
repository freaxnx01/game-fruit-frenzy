# Fruit Frenzy 🍒💥

A physics-based **fruit-merge arcade game** (Suika-style "drop & merge") with chain
combos and an area-clearing bomb. Aim, drop a fruit into the box, and when two of the
same tier touch they **merge** into the next-larger fruit — cherry → berry → grape →
… → **watermelon**. Merge quickly to build a **combo**; a 3-chain earns a **Frenzy
Bomb** that explodes on contact and clears everything nearby. Let the pile rise above
the dashed danger line and it's game over.

**▶️ Play it: https://github.freaxnx01.ch/game-fruit-frenzy/**

## How to Play

| Action | How |
| --- | --- |
| Aim | Move the mouse (or drag your finger) across the board |
| Drop | Click or tap |

- **Merge** two fruits of the same tier to make the next one up. Two watermelons cancel
  out for a big bonus.
- **Chain** merges within ~1.6 s to raise the combo multiplier — points scale with it.
- **Frenzy Bomb**: reach a 3-chain and your next drop becomes a violet bomb that blows
  up the first thing it hits, clearing a wide radius.
- **Stay under the dashed line.** If fruit rests above it too long, the game ends.

Your best score is saved locally in the browser.

## Tech

- **Single self-contained `index.html`.** All game logic, Canvas 2D rendering, physics,
  and sound live in one file — no build step, no server, no external asset files.
- **Canvas-drawn everything.** Every fruit, face, leaf, particle and the bomb are drawn
  at runtime; all sound is synthesized with the Web Audio API. The only network
  dependency is the *Baloo 2* web font from Google Fonts (falls back to a system sans
  offline).
- **Deterministic-ish arcade physics.** Fixed 480×640 world, gravity + circle collisions
  with restitution, mass ∝ r², run in substeps per animation frame.

## Running Locally

`index.html` is fully self-contained, so serving the folder is enough:

```sh
# from the repo root
python3 -m http.server 8000
# then visit http://localhost:8000/
```

## License

No license file yet — all rights reserved by default. Ask if you'd like to reuse it.

---

*`source/Fruit Frenzy.dc.html` is the original design-tool export, kept for reference
only — it isn't used by the deployed game.*
