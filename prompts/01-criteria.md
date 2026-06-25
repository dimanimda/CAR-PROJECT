# Approach 01 — criteria

Baseline prompt + explicit acceptance criteria appended. Tests the hypothesis: does stating the rubric *inside* the prompt raise quality? The criteria below are aligned with `../RUBRIC.md` so we can see whether the model self-satisfies what we measure.

---

Write a single HTML file with a full-page canvas and no libraries. Simulate a realistic side-view of a moving car as the main subject. Keep the car visible in the foreground while the background landscape scrolls continuously to create the feeling that the car is driving forward. Use layered scenery for depth: nearby ground, roadside elements, trees, poles, and distant hills or mountains should move at different speeds for a natural parallax effect. Animate the wheels spinning realistically and add subtle body motion so the car feels connected to the road. Let the environment pass smoothly behind it, with repeating but varied scenery that makes the movement feel believable. Use cinematic lighting and a cohesive sky, such as sunset, dusk, or daylight, to enhance atmosphere. The overall motion should feel calm, immersive, and realistic, with a seamless looping animation.

## Acceptance criteria (the result MUST satisfy all of these)

1. **Single file, zero libraries** — one `.html` file, no `<script src=>`, no CDN, no `import`. All JS inline.
2. **Clean console** — zero errors or warnings in the browser console on load and during animation.
3. **Full-page canvas** — canvas fills the viewport and resizes correctly on window resize (no fixed pixel size).
4. **Parallax depth** — at least 3 background layers (ideally 4+) moving at clearly different speeds: distant hills slowest, near ground fastest.
5. **Seamless loop** — scrolling layers wrap with no visible jump, tear, or gap at the seam. The animation must loop forever cleanly.
6. **Wheels rotate** — both wheels visibly spin, at an angular speed consistent with the forward motion of the scenery.
7. **Subtle body motion** — the car body has a small, believable bob/sway so it feels connected to the road (not rigid, not exaggerated).
8. **Cohesive sky & lighting** — a single coherent time-of-day palette (sunset / dusk / daylight); scenery colors and shadows match that light.
9. **Smooth motion** — targets ~60fps via `requestAnimationFrame`; no stutter, no busy-wait, no `setInterval` for the render loop.
10. **Calm & immersive** — the overall feel is calm and realistic, not arcade-like or jittery.

Before finishing, mentally verify each criterion against your output.
