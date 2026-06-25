Build a single self-contained HTML file (full-page canvas, no libraries) that shows a car driving with a parallax background and a seamless loop. Construct it incrementally — implement these stages in order, and make sure each stage actually works and is visually correct before adding the next. Each stage should leave a runnable file.

Stage 1 — Skeleton. Full-page canvas that resizes to the viewport. A requestAnimationFrame loop that clears the frame each tick using delta-time. Confirm it runs with an empty scene.

Stage 2 — Sky. Draw a static vertical gradient sky with a coherent time-of-day palette (sunset or dusk) and a soft sun. Confirm the palette reads as cohesive.

Stage 3 — One scrolling layer. Add the near ground/road as a single horizontal layer that scrolls left using x % tileWidth, tiled at least twice. Verify the wrap is perfectly seamless — no jump or gap at the seam. Do not proceed until the seam is clean.

Stage 4 — Parallax depth. Add three more layers behind the ground — distant hills (slowest), a far tree line, and roadside poles — each scrolling at a clearly different, slower speed than the ground. Confirm depth reads naturally and every layer wraps seamlessly.

Stage 5 — Static car. Draw a recognizable side-view car in the foreground, sitting on the road line, occupying a substantial part of the frame. Get the silhouette right before animating.

Stage 6 — Wheels. Animate both wheels rotating, with rotation speed consistent with the ground scroll speed. Make the rotation visible (spokes / hub mark).

Stage 7 — Body motion. Add a small, believable vertical bob to the car body so it feels connected to the road — subtle, not bouncy.

Stage 8 — Polish. Tune lighting, shadows and color so the whole scene feels calm, immersive, cinematic, and the loop is seamless forever.

Return the final single HTML file after Stage 8. Zero console errors.
