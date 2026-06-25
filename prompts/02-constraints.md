# Approach 02 — constraints

Baseline intent + **content-aware constraints**: explicit numbers, proportions and speeds. Counters model "content-blindness" — instead of vague adjectives ("realistic", "subtle"), it pins concrete quantities the model would otherwise guess. Tests whether hard numbers produce a more controlled, consistent result.

---

Write a single HTML file with a full-page `<canvas>` and no external libraries (all JS inline). Render a realistic side-view of a car driving forward, with a continuously scrolling parallax landscape behind it and a seamless infinite loop. Follow these concrete specifications:

### Canvas & loop
- Canvas fills the full viewport; on `window.resize` update its width/height to `innerWidth`/`innerHeight`.
- Single render loop driven by `requestAnimationFrame`. Use elapsed time (delta) for motion so speed is frame-rate independent.

### Scene layout (relative to canvas height H and width W)
- Horizon / ground line at ~72% of H.
- Sky occupies the top ~72%, ground the bottom ~28%.

### Parallax layers (back to front), each scrolled by `x % layerWidth` for a seamless wrap
1. **Distant hills/mountains** — scroll speed factor **0.10**.
2. **Far tree line** — factor **0.30**.
3. **Roadside poles** — factor **0.60**, evenly spaced ~220px apart.
4. **Near ground / road texture** — factor **1.00** (reference speed).
Each layer must be drawn at least twice (tiled) so wrapping leaves no gap.

### Car (the foreground subject)
- Width ≈ **28% of W**, horizontally centered slightly left (center at ~45% of W).
- Body sits just above the ground line; baseline of wheels touches the road.
- **Two wheels**, each rotating with angular velocity matched to ground scroll: `angle += groundSpeed * dt / wheelRadius`. Draw spokes or a hub mark so rotation is visible.
- **Body bob**: vertical offset `sin(t * 2.5) * 2` px (≈ ±2px) so it feels connected to the road without bouncing.

### Lighting & sky
- Vertical gradient sky, sunset palette: deep orange near the horizon → warm pink → dusky blue at the top. Include a soft sun disc near the horizon.
- Scenery silhouettes darker toward the foreground; warm rim light from the sun direction.

Deliver one self-contained `.html` file, zero console errors.
