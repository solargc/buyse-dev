+++
title = "cub3d"
date = 2025-09-01
+++

A first-person maze inspired by Wolfenstein 3D. The goal of this 42 project was to build a simple raycasting engine. As a team, we implemented parsing,  movement, rotation and textures.

<iframe
  src="https://solargc.github.io/cub3d-wasm/"
  class="embed-frame"
  style="width: 100%; aspect-ratio:16/9"
  loading="lazy"
  allow="fullscreen" allowfullscreen>
</iframe>

This WASM demo is interactive on both desktop and mobile and supports fullscreen mode.
<div class="desktop-only">
Use the keys shown below to move and look around.
</div>
<div class="mobile-only">
Use two thumbs: left side to move, right side to look around.
</div>

<div class="controls" style="padding-top: 1em">
    <div class="keys">
        <div class="key-row">
            <kbd>W</kbd>
        </div>
        <div class="key-row">
            <kbd>A</kbd>
            <kbd>S</kbd>
            <kbd>D</kbd>
        </div>
    </div>
    <div class="keys">
        <div class="key-row">
            <kbd>&larr;</kbd>
            <kbd>&rarr;</kbd>
        </div>
    </div>
</div>

I learned about:

- Parsing and validating map files
- Checking map integrity, error handling
- Using a low-level graphics library and event loop
- Implementing raycasting with the DDA algorithm
- Frame rendering with textured walls
- Movement, collision detection, keybindings

Textures were hand-crafted by Jacobus.   
The original C project is [here](https://github.com/solargc/cub3d).  
Claude was used for the WASM compilation.  
