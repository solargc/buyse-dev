+++
title = "galactyl 3000"
date = 2026-03-11

[extra]
thumbnail = "thumbnail.jpg"
+++

A typing game where every keystroke propels you through a space.  
It is written in Typescript/React/CSS.

<iframe
  src="https://solargc.github.io/galactyl-3000"
  class="embed-frame"
  style="width: 100%; aspect-ratio:5/4"
  loading="lazy"
  allow="fullscreen" allowfullscreen>
</iframe>

*Warning: this game contains flashing lights.*

Start the game by typing but make sure the window is focused.  
It is desktop only and supports fullscreen.

What I learned:

- Projecting 3D coordinates to 2D to create depth and movement
- CSS transformations: perspective(), rotateX(), scaleY()
- Creating a gameplay with speed, shake, color shifts tied to input
- Escalating effects to create tension
- Responsive layout, media queries on both width and height
- Automating deployment of a Vite/React app with GitHub Actions

This was done mostly with Claude.  
The goal was to play with modern CSS and automated workfklows.  
Code is [here](https://github.com/solargc/galactyl-3000).  
