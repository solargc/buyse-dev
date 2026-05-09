+++
title = "bahut"
date = 2026-05-08

[extra]
thumbnail = "fig_01.jpg"
+++

With the experience gained from [tabletango](/projects/tabletango/), I kept the same core stack and built a book sharing app for a local book club. I wanted the onboarding to be as simple as possible with token-based authentification. Access grows as a tree of trust: any member can invite a friend into their shelf.

The group shares a shelf (a library), you can add books scanning their ISBN code and follow who reads which book. You can be part of multiple shelves and create new ones, with rate limiting to keep things stable. It is deployed and in early testing at the book club.

<style>
.sg-r { display: none; }
.sg .slide { display: none; }
#r1:checked ~ .sg .slide:nth-child(1),
#r2:checked ~ .sg .slide:nth-child(2),
#r3:checked ~ .sg .slide:nth-child(3),
#r4:checked ~ .sg .slide:nth-child(4),
#r5:checked ~ .sg .slide:nth-child(5),
#r6:checked ~ .sg .slide:nth-child(6),
#r7:checked ~ .sg .slide:nth-child(7) { display: block; }
.slide-wrap {
  position: relative;
  width: 70%; min-width: 300px;
  margin: 2em 0 0.5em;
}
.slide-wrap img {
  display: block; width: 100%;
  border: 2px solid var(--foreground);
  border-radius: 10px;
}
.slide-arr {
  position: absolute; bottom: 0.6em;
  font-size: 1.2em; line-height: 1;
  padding: 0.15em 0.4em;
  background: var(--accent);
  border: 1px solid var(--background);
  border-radius: 4px;
  cursor: pointer;
  color: var(--background);
  opacity: 0.8;
}
.slide-arr.l { left: 0.6em; }
.slide-arr.r { right: 0.6em; }
.slide-arr:hover { background: var(--accent-highlight); }
.slide-num {
  width: 70%; min-width: 300px;
  text-align: center;
  margin: 0.4em 0 2em;
}
</style>

<input class="sg-r" type="radio" name="sg" id="r1" checked>
<input class="sg-r" type="radio" name="sg" id="r2">
<input class="sg-r" type="radio" name="sg" id="r3">
<input class="sg-r" type="radio" name="sg" id="r4">
<input class="sg-r" type="radio" name="sg" id="r5">
<input class="sg-r" type="radio" name="sg" id="r6">
<input class="sg-r" type="radio" name="sg" id="r7">

<div class="sg">
  <div class="slide">
    <div class="slide-wrap">
      <img src="fig_01.jpg" alt="figure 1 of 7">
      <label class="slide-arr l" for="r7">&larr;</label>
      <label class="slide-arr r" for="r2">&rarr;</label>
    </div>
    <p class="secondary small slide-num">1 / 7</p>
  </div>
  <div class="slide">
    <div class="slide-wrap">
      <img src="fig_02.jpg" alt="figure 2 of 7">
      <label class="slide-arr l" for="r1">&larr;</label>
      <label class="slide-arr r" for="r3">&rarr;</label>
    </div>
    <p class="secondary small slide-num">2 / 7</p>
  </div>
  <div class="slide">
    <div class="slide-wrap">
      <img src="fig_03.jpg" alt="figure 3 of 7">
      <label class="slide-arr l" for="r2">&larr;</label>
      <label class="slide-arr r" for="r4">&rarr;</label>
    </div>
    <p class="secondary small slide-num">3 / 7</p>
  </div>
  <div class="slide">
    <div class="slide-wrap">
      <img src="fig_04.jpg" alt="figure 4 of 7">
      <label class="slide-arr l" for="r3">&larr;</label>
      <label class="slide-arr r" for="r5">&rarr;</label>
    </div>
    <p class="secondary small slide-num">4 / 7</p>
  </div>
  <div class="slide">
    <div class="slide-wrap">
      <img src="fig_05.jpg" alt="figure 5 of 7">
      <label class="slide-arr l" for="r4">&larr;</label>
      <label class="slide-arr r" for="r6">&rarr;</label>
    </div>
    <p class="secondary small slide-num">5 / 7</p>
  </div>
  <div class="slide">
    <div class="slide-wrap">
      <img src="fig_06.jpg" alt="figure 6 of 7">
      <label class="slide-arr l" for="r5">&larr;</label>
      <label class="slide-arr r" for="r7">&rarr;</label>
    </div>
    <p class="secondary small slide-num">6 / 7</p>
  </div>
  <div class="slide">
    <div class="slide-wrap">
      <img src="fig_07.jpg" alt="figure 7 of 7">
      <label class="slide-arr l" for="r6">&larr;</label>
      <label class="slide-arr r" for="r1">&rarr;</label>
    </div>
    <p class="secondary small slide-num">7 / 7</p>
  </div>
</div>



**Backend in Rust**

  - [Axum](https://github.com/tokio-rs/axum) for routing, REST API with UUID token-based
  auth
  - [SQLx](https://github.com/launchbadge/sqlx) with compile-time verified SQL queries
  against PostgreSQL
  - [reqwest](https://github.com/seanmonstar/reqwest) to fetch book metadata from the [Open
   Library](https://openlibrary.org) API

  **Frontend with Svelte**

  - [Svelte 5](https://svelte.dev) (Runes)
  - TypeScript
  - Vite
  - [zxing-wasm](https://github.com/Sec-ant/zxing-wasm) for in-browser barcode scanning

  **Infrastructure**

  - PostgreSQL
  - Hetzner VPS configured with NixOS and [disko](https://github.com/nix-community/disko)
  - [Caddy](https://caddyserver.com) as reverse proxy with automatic HTTPS
  - Rust binary built declaratively with [Crane](https://github.com/ipetkov/crane) + Nix flakes
  - Secret management with [sops-nix](https://github.com/Mic92/sops-nix)
  - Remote deployments over SSH with [deploy-rs](https://github.com/serokell/deploy-rs)

**Llm collegue**
- Claude used throughout development and NixOS config for deployment.

**Todo**
- Scheduled database backups
