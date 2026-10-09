# KANAPE: OUTLAND

**Third-person low-poly survival sandbox.** This repository now contains a playable browser-game foundation: explore an abandoned field station, move through a compact environment, and secure five supply caches.

> Build 0.1.0 — playable prototype, not a finished survival game.

## Run

Serve the repository root with any static HTTP server. Example:

```bash
python -m http.server 8000
```

Open `http://localhost:8000`. Do not open `index.html` through `file://`; browser module loading may be blocked.

The first load needs an internet connection for the Three.js ES module and web fonts.

## Controls

| Input | Action |
| --- | --- |
| W / A / S / D | Move relative to camera |
| Mouse | Orbit third-person camera |
| Shift | Sprint; consumes stamina |
| Space | Jump |
| E | Collect nearby supplies |
| Esc | Pause / resume |
| Mobile joystick | Move |
| Drag on right side | Look around on touch screens |
| Mobile buttons | Jump / interact |

## Implemented

- Third-person follow camera with smoothing, ground-height safety clamp, and raycast-based obstacle avoidance.
- Controllable survivor with procedural walk/run movement, sprint stamina and jumping.
- Separate invisible player collision volume and simple obstacle collision.
- Low-poly outdoor environment with abandoned house, shed, road, cover and trees.
- Five collectible supply caches, inventory counter and objective completion.
- Minimal HUD, pause overlay and responsive touch controls.
- No account, backend, API key or build step.

## Technology

- Three.js ES modules from jsDelivr.
- Plain JavaScript and CSS.
- GitHub Pages static deployment via GitHub Actions.
- All local asset paths are relative, so the site can run under a repository subpath.

## GitHub Pages

Open **Settings → Pages** and select **GitHub Actions** as the deployment source if it is not already selected. The workflow at `.github/workflows/pages.yml` publishes the repository root.

## Known prototype limits

- The survivor is procedural geometry; a rigged GLB and genuine skeletal locomotion clips are not yet integrated.
- Player obstacle handling currently uses axis-separated AABB checks rather than a full capsule-cast physics controller.
- The camera avoids the current solid box colliders, but complex foliage and non-solid scenery do not block the view.

## Planned next

1. Import and verify a rigged GLB survivor and genuine locomotion animations.
2. Upgrade obstacle handling to capsule casts and a physics engine.
3. Add resource types, pickup feedback, inventory slots and crafting.
4. Add save/load and world-state persistence.
5. Profile mobile performance and improve environment streaming.

Planned items are not represented as implemented features.
