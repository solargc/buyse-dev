+++
title = "galactyl 3000"
date = 2026-03-11

[extra]
thumbnail = "thumbnail.jpg"
+++

A typing game where every keystroke propels you through a space.
Type fast, watch planets fly by, and survive the countdown.
It is written in Typescript/React/CSS.

<iframe
  src="https://solargc.github.io/galactyl-3000"
  class="embed-frame"
  style="width: 100%; aspect-ratio:5/4"
  loading="lazy"
  allow="fullscreen" allowfullscreen>
</iframe>


What I learned:

- Canvas-based animations: projecting 3D coordinates to 2D to create depth illusions
- CSS transformations: perspective(), rotateX(), scaleY()
- Gameplay feel: tying visual feedback (speed, shake, color shifts) directly to player input
- Progressive tension design: escalating effects as the timer runs out to create urgency
- Responsive layout: media queries on both width and height, flex container sizing pitfalls
- Deploying a Vite/React app to GitHub Pages with GitHub Actions

This was done mostly with Claude.
