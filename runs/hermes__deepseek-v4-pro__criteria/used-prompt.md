Write a single HTML file with a full-page canvas and no libraries. Simulate a realistic side-view of a moving car as the main subject. Keep the car visible in the foreground while the background landscape scrolls continuously to create the feeling that the car is driving forward. Use layered scenery for depth: nearby ground, roadside elements, trees, poles, and distant hills or mountains should move at different speeds for a natural parallax effect. Animate the wheels spinning realistically and add subtle body motion so the car feels connected to the road. Let the environment pass smoothly behind it, with repeating but varied scenery that makes the movement feel believable. Use cinematic lighting and a cohesive sky, such as sunset, dusk, or daylight, to enhance atmosphere. The overall motion should feel calm, immersive, and realistic, with a seamless looping animation.

## Acceptance criteria (the result MUST satisfy all of these)

1. Single file, zero libraries — one .html, no <script src=>, no CDN, no import. All JS inline.
2. Clean console — zero errors or warnings on load and during animation.
3. Full-page canvas — fills the viewport and resizes correctly (no fixed pixel size).
4. Parallax depth — at least 3 (ideally 4+) background layers at clearly different speeds; distant slowest, near ground fastest.
5. Seamless loop — scrolling layers wrap with no visible jump/tear/gap; loops forever cleanly.
6. Wheels rotate — both wheels visibly spin at an angular speed consistent with the scenery's forward motion.
7. Subtle body motion — small believable bob/sway so the car feels connected to the road.
8. Cohesive sky & lighting — single coherent time-of-day palette; scenery colors/shadows match the light.
9. Smooth motion — ~60fps via requestAnimationFrame; no stutter, no setInterval render loop.
10. Calm & immersive — overall feel is calm and realistic, not arcade-like.

Before finishing, verify each criterion against the output.
