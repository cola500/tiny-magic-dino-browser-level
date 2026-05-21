# Tiny Magic Dino — Browser Level

A tiny browser game built end-to-end in ~10 minutes as an AI-assisted rapid prototyping experiment.

**Play it live:** https://cola500.github.io/tiny-magic-dino-browser-level/

## What this experiment tested

> Hypothesis: We can use AI-assisted rapid prototyping to create a small, emotionally engaging browser game slice in under 20 minutes — without Unity, build tooling, or dependencies.

**Result: Confirmed.** A single `index.html` with Canvas + a bit of CSS was enough to ship a playable, charming demo. Total build time: ~10 minutes.

See [`HYPOTHESIS.md`](./HYPOTHESIS.md) for the full experiment write-up (scope, success criteria, what was intentionally faked, manual verification).

## What it is

A side-scrolling mini-level where you control a friendly dinosaur, collect the letters `L-I-N-D-E-N-G-A-R-D`, jump over two chasms, and reach the finish flag.

- Side-scrolling with parallax background
- Two chasms, three floating platforms
- Ten collectible letter-coins with glow
- Forgiving respawn (keeps collected letters)
- Win screen with confetti

## Controls

**Desktop:**
- `Space` or `↑` — jump
- `←` `→` — run
- `R` — restart after winning

**Mobile / touch:**
- Tap **HOPPA** to jump
- Hold **◀** / **▶** to run left / right
- Touch controls appear automatically on touch devices
- Desktop keyboard still works in parallel

## Mobile support

The game scales responsively and shows a thumb-friendly control bar at the bottom of the screen on touch devices. Tested patterns:

- Viewport locked (no pinch-zoom, no pull-to-refresh)
- Canvas keeps its 2:1 aspect ratio and scales to screen width
- Letter HUD shrinks on small screens
- Touch buttons sit above the iOS home-indicator safe area

### Mobile verification checklist
- [ ] Open the Pages URL on a phone — page loads without horizontal scroll
- [ ] HUD with 10 letter slots is visible above the canvas
- [ ] Tapping **HOPPA** makes the dino jump
- [ ] Holding **▶** runs the dino right
- [ ] Holding **◀** runs the dino left
- [ ] Scrolling the page is locked while playing (no accidental jumps from drag)
- [ ] You can complete the level: collect all letters, reach the flag, see the win screen with confetti

## How to run locally

No build step. No dependencies. No package manager. Just open the file:

```sh
open index.html
```

Or double-click `index.html` in Finder.

## How it was made

Built collaboratively with Claude Code as a "tiny experiment" — one HTML file, no frameworks, no tooling. The full hypothesis-driven approach is documented in [`HYPOTHESIS.md`](./HYPOTHESIS.md).

This repo is intentionally tiny. Everything lives in `index.html`.
