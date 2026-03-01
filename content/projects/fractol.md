+++
title = "fractol"
date = 2025-01-08
+++

A small graphics program in C that renders fractals like Mandelbrot and Julia sets.

<iframe
  src="https://solargc.github.io/fractol-wasm/"
  class="embed-frame"
  style="width: 100%; aspect-ratio:1/1"
  loading="lazy">
</iframe>

This WASM demo is interactive on desktop and mobile.

<div class="controls-grid desktop-only">
    <span>Move</span>
    <div class="keys-inline"><kbd>H</kbd><kbd>J</kbd><kbd>K</kbd><kbd>L</kbd></div>
    <span>Julia X</span>
    <div class="keys-inline"><kbd>X</kbd><kbd>C</kbd></div>
    <span>Zoom</span>
    <div class="keys-inline"><kbd>=</kbd><kbd>-</kbd><span class="sep"> or </span><kbd>ctrl</kbd><span class="sep">+</span><kbd>scroll</kbd></div>
    <span>Julia Y</span>
    <div class="keys-inline"><kbd>Y</kbd><kbd>U</kbd></div>
    <span>Iterations</span>
    <div class="keys-inline"><kbd>I</kbd><kbd>O</kbd></div>
    <span>Theme</span>
    <div class="keys-inline"><kbd>T</kbd><span class="sep"> or </span><kbd>right click</kbd></div>
    <span>Reset</span>
    <div class="keys-inline"><kbd>R</kbd></div>
    <span>Switch set</span>
    <div class="keys-inline"><kbd>S</kbd><span class="sep"> or </span><kbd>left click</kbd></div>
</div>
<div class="controls-grid mobile-only">
    <span>Move</span>
    <span>drag</span>
    <span>Zoom</span>
    <span>pinch</span>
    <span>Switch set</span>
    <span>tap</span>
    <span>Theme</span>
    <span>double tap</span>
</div>

<div class="space"></div>

What I learned:
- Understanding Mandelbrot and Julia fractals
- Working with complex numbers, iterations, coordinate mapping
- Pixel rendering, frame buffering with a low-level graphics library
- Implementing zoom, pan, interactive controls
- Handling keyboard and mouse events
