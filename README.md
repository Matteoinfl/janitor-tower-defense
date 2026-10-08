# Jimmy the Janitor: Tower Defense

> A retro, NES-style tower defense game where a janitor hero defends an office building from rats, roaches, walking poop and dirty toilets. One plain HTML5/JavaScript codebase runs as a Windows app, in any browser, and on iPhone.

**When:** September 2026
**Stack:** HTML5 Canvas · vanilla JavaScript · Electron (Windows .exe) · PWA (iPhone home screen) · Node.js test harness
**My role:** Game design and direction, playtesting and balancing. Built with Claude Code as an AI pair programmer.

> Made as a fun branded game for my workplace, so the repository stays private. This page describes the game and how it's built.

---

## The game

Messes stream in from the loading dock and try to reach the lobby before the health inspector arrives. You:

- Build cleaning-gear towers (spray bottle, mop bucket, plunger launcher, shop vac), each with **3 upgrade paths × 4 tiers**
- Place walls (wet floor signs, snack cans, caution tape) to **reroute the messes into longer paths**; you can't fully block the route
- Move Jimmy around the map; he auto-swats, levels up and has two special abilities
- Survive 20 waves and a boss

The humor is aimed at kids: banana peels, roaches on Jimmy's face, fart sounds and a boss that poops out more poop.

## How it's built

- **Simulation separate from drawing.** The game logic (pathfinding, combat, waves) has no DOM code, so it can run headless in tests.
- **Dijkstra flow-field pathfinding** recomputed as you build, with a rule that stops you from sealing the path.
- **All art, the bitmap font and every sound effect are generated in code.** No outside assets.
- Renders a 480×270 logical screen on a 2× canvas so sprites get extra detail.
- Ships as a Windows .exe (Electron), a browser game, and an iPhone home-screen app, plus a 5-wave website demo mode.

## Testing

A headless harness with **219 automated checks**, including bot playthroughs. After I playtested early builds, the bots helped tune the economy so a random-placement bot wins about half its runs.

## Iterating from playtests

Each round of my playtesting led to a pass: bigger art and a simpler interface; a next-wave preview and early-call bonus; "NEW MESS!" intro cards; towers that visibly change at higher tiers; and a 2× detail pass on every sprite.

---

*See also the [janitor arcade](https://github.com/Matteoinfl/janitor-arcade) that reuses these characters. More projects on my [profile](https://github.com/Matteoinfl).*
