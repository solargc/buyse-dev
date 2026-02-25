+++
title = "cub3d"
date = 2025-09-01
+++

A first-person maze inspired by Wolfenstein 3D. The goal of this 42 project was to build a simple raycasting engine. As a team, we implemented parsing,  movement, rotation and textures.

<iframe
  src="https://solargc.github.io/cub3d-wasm/"
  class="embed-frame"
  style="width: 100%; aspect-ratio:16/9"
  loading="lazy">
</iframe>

<div class="controls">
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

With this graphics project, we learned a lot:

- File parsing and error handling
- Event loop and graphics library usage
- DDA algorithm for raycasting
- Frame rendering, movement and keybindings

Textures were hand-crafted by Jacobus.   
The original C project is [here](https://github.com/solargc/cub3d).  
Claude was used for the WASM compilation.  
