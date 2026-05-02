+++
title = "tabletango"
date = 2026-04-20

[extra]
thumbnail = "fig_01.jpg"
+++

I built this project to explore further full stack development. A lot is new territory: Axum for routing, async Rust, reactive frontends, SSR vs CSR, infrastructure-as-code. Running NixOS as daily driver helped greatly for declarative deployment.

This is a platform to help restaurants to manage reservations. The project includes a live dashboard with reservations, configurable customer booking pages, table and schedule management, gift cards, device pairing via QR code.

<style>
.sg-r { display: none; }
.sg .slide { display: none; }
#r1:checked ~ .sg .slide:nth-child(1),
#r2:checked ~ .sg .slide:nth-child(2),
#r3:checked ~ .sg .slide:nth-child(3),
#r4:checked ~ .sg .slide:nth-child(4),
#r5:checked ~ .sg .slide:nth-child(5) { display: block; }
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

<div class="sg">
  <div class="slide">
    <div class="slide-wrap">
      <img src="fig_01.jpg" alt="figure 1 of 5">
      <label class="slide-arr l" for="r5">&larr;</label>
      <label class="slide-arr r" for="r2">&rarr;</label>
    </div>
    <p class="secondary small slide-num">1 / 5</p>
  </div>
  <div class="slide">
    <div class="slide-wrap">
      <img src="fig_02.jpg" alt="figure 2 of 5">
      <label class="slide-arr l" for="r1">&larr;</label>
      <label class="slide-arr r" for="r3">&rarr;</label>
    </div>
    <p class="secondary small slide-num">2 / 5</p>
  </div>
  <div class="slide">
    <div class="slide-wrap">
      <img src="fig_03.jpg" alt="figure 3 of 5">
      <label class="slide-arr l" for="r2">&larr;</label>
      <label class="slide-arr r" for="r4">&rarr;</label>
    </div>
    <p class="secondary small slide-num">3 / 5</p>
  </div>
  <div class="slide">
    <div class="slide-wrap">
      <img src="fig_04.jpg" alt="figure 4 of 5">
      <label class="slide-arr l" for="r3">&larr;</label>
      <label class="slide-arr r" for="r5">&rarr;</label>
    </div>
    <p class="secondary small slide-num">4 / 5</p>
  </div>
  <div class="slide">
    <div class="slide-wrap">
      <img src="fig_05.jpg" alt="figure 5 of 5">
      <label class="slide-arr l" for="r4">&larr;</label>
      <label class="slide-arr r" for="r1">&rarr;</label>
    </div>
    <p class="secondary small slide-num">5 / 5</p>
  </div>
</div>

**Backend in Rust**

- [Axum](https://github.com/tokio-rs/axum) for routing, REST API with token-based auth
- [SQLx](https://github.com/launchbadge/sqlx) with compile-time verified SQL queries against PostgreSQL
- [Tokio](https://tokio.rs) broadcast channels for real-time dashboard events

**Frontend with SvelteKit**

- Svelte 5 (Runes)
- TypeScript
- Tailwind CSS

**Infrastructure**

- PostgreSQL in Docker locally, NixOS service in production
- Hetzner VPS reformatted to NixOS with [nixos-anywhere](https://github.com/nix-community/nixos-anywhere)
- [Caddy](https://caddyserver.com) as reverse proxy with automatic HTTPS
- Rust binary built reproducibly with [Crane](https://github.com/ipetkov/crane) + Nix flakes
- Remote deployments over ssh with [deploy-rs](https://github.com/serokell/deploy-rs)

**Llm collegue**
- Claude used throughout development and NixOS config for deployment.

**Todo**
- Secret management with [sops-nix](https://github.com/Mic92/sops-nix)
