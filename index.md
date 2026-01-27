---
layout: single
title: ""
permalink: /
author_profile: true
classes: wide
---

# Featured research themes

I study how **temporal structure of environmental extremes** shapes **benthic invertebrate performance and variability**, combining **mesocosm experiments**, **behavioural/physiological measurements**, and **mechanistic/statistical modelling**.

<div class="zq-grid">

  <a class="zq-card zq-card-link" data-accent="warm" href="https://doi.org/10.1002/lno.12332" target="_blank" rel="noopener" aria-label="Marine heatwaves (opens in new tab)">
    <div class="zq-card__top">
      <span class="zq-icon" aria-hidden="true">🔥</span>
      <span class="zq-pill">Marine heatwaves</span>
    </div>
    <div class="zq-body">
      How timing, duration, and variability of heat events reshape physiology and behaviour—beyond mean responses.
    </div>
    <div class="zq-meta">Focus: temporal heatwave structure · performance shifts · behavioural responses</div>
  </a>

  <a class="zq-card zq-card-link" data-accent="cool" href="https://doi.org/10.1002/lno.12669" target="_blank" rel="noopener" aria-label="Behaviour–sediment coupling (opens in new tab)">
    <div class="zq-card__top">
      <span class="zq-icon" aria-hidden="true">⚙️</span>
      <span class="zq-pill">Behaviour–sediment coupling</span>
    </div>
    <div class="zq-body">
      Quantifying bioturbation processes and feedbacks that control sediment stability on tidal flats.
    </div>
    <div class="zq-meta">Focus: mobility traits · sediment mixing · ecosystem feedbacks</div>
  </a>

  <a class="zq-card zq-card-link" data-accent="mint" href="https://doi.org/10.1016/j.gecco.2025.e03918" target="_blank" rel="noopener" aria-label="Compound extremes & invasion outcomes (opens in new tab)">
    <div class="zq-card__top">
      <span class="zq-icon" aria-hidden="true">📈</span>
      <span class="zq-pill">Compound extremes &amp; invasion outcomes</span>
    </div>
    <div class="zq-body">
      How compound extreme events shift survival and behaviour trade-offs between native and introduced bivalves.
    </div>
    <div class="zq-meta">Focus: compound events · mortality · burrowing behaviour · establishment windows</div>
  </a>

  <a class="zq-card zq-card-link" data-accent="violet" href="https://github.com/zqzhou7" target="_blank" rel="noopener" aria-label="Reproducible workflows on GitHub (opens in new tab)">
    <div class="zq-card__top">
      <span class="zq-icon" aria-hidden="true">🧰</span>
      <span class="zq-pill">Reproducible workflows</span>
    </div>
    <div class="zq-body">
      Clean pipelines for experiments, visualization, and analysis—designed for traceability and re-use.
    </div>
    <div class="zq-meta">Focus: R/Python · GitHub · data templates · automation</div>
  </a>

</div>

<style>
/* =========================================================
   ZQ Home Cards — “Liquid Glass” (air-light / air-dark)
   Dark mode selector: html[data-theme="dark"]
   ========================================================= */

/* Grid */
.zq-grid{
  display:grid;
  grid-template-columns: 1fr 1fr;
  gap: 16px;
  margin-top: 18px;
}
@media (max-width: 780px){
  .zq-grid{ grid-template-columns: 1fr; }
}

/* Accent tokens (RGB triplets) */
:root{
  --zq-warm: 255, 99, 72;     /* coral */
  --zq-cool: 0, 122, 255;     /* iOS blue */
  --zq-mint: 52, 199, 89;     /* iOS green */
  --zq-violet: 175, 82, 222;  /* iOS purple */
}

/* Card base: liquid glass (NOT white sticker) */
.zq-card{
  position: relative;
  overflow: hidden;
  border-radius: 22px;
  padding: 18px 18px 16px 18px;

  /* key: lower opacity so page background comes through */
  background: rgba(255,255,255,0.28);
  border: 1px solid rgba(0,0,0,0.08);

  /* softer shadow so it feels embedded in “air” theme */
  box-shadow:
    0 18px 50px rgba(0,0,0,0.10),
    0 1px 0 rgba(255,255,255,0.65) inset;

  backdrop-filter: blur(18px) saturate(140%);
  -webkit-backdrop-filter: blur(18px) saturate(140%);

  transition: transform 180ms ease, box-shadow 180ms ease, border-color 180ms ease;
}

/* Liquid highlight + edge shine */
.zq-card::before{
  content:"";
  position:absolute;
  inset: 0;
  pointer-events:none;
  border-radius: 22px;

  /* specular highlight sweep */
  background: radial-gradient(1200px 260px at 30% 0%,
      rgba(255,255,255,0.65),
      rgba(255,255,255,0.14) 45%,
      rgba(255,255,255,0.00) 70%);
  opacity: 0.75;
}

/* Colored “ink” glow inside each card (subtle, not neon) */
.zq-card::after{
  content:"";
  position:absolute;
  inset:-40px;
  pointer-events:none;
  border-radius: 26px;
  opacity: 0.55;

  background:
    radial-gradient(380px 220px at 18% 18%, rgba(var(--zq-accent), 0.22), rgba(255,255,255,0) 60%),
    radial-gradient(420px 260px at 88% 38%, rgba(var(--zq-accent), 0.14), rgba(255,255,255,0) 62%),
    radial-gradient(520px 320px at 50% 105%, rgba(0,0,0,0.06), rgba(255,255,255,0) 60%);
  filter: blur(2px);
}

/* Hover = gentle lift (macOS-like) */
.zq-card:hover{
  transform: translateY(-3px);
  border-color: rgba(0,0,0,0.12);
  box-shadow:
    0 26px 70px rgba(0,0,0,0.14),
    0 1px 0 rgba(255,255,255,0.70) inset;
}

/* Make entire card clickable, remove underlines */
.zq-card-link{
  display:block;
  text-decoration: none !important;
}
.zq-card-link *{
  text-decoration: none !important;
}
.zq-card-link:focus{ outline: none; }
.zq-card-link:focus-visible{
  outline: 3px solid rgba(0,122,255,0.35);
  outline-offset: 5px;
  border-radius: 24px;
}

/* Top row */
.zq-card__top{
  display:flex;
  align-items:center;
  gap: 10px;
  margin-bottom: 10px;
  position: relative;
  z-index: 2;
}

/* Icon (slightly glassy) */
.zq-icon{
  width: 34px;
  height: 34px;
  display:inline-flex;
  align-items:center;
  justify-content:center;
  border-radius: 12px;

  background: rgba(255,255,255,0.22);
  border: 1px solid rgba(0,0,0,0.07);
  box-shadow: 0 10px 26px rgba(0,0,0,0.06);
  font-size: 18px;
}

/* Accent pill */
.zq-pill{
  font-weight: 700;
  font-size: 0.95rem;
  letter-spacing: 0.1px;

  padding: 7px 12px;
  border-radius: 999px;

  background: rgba(255,255,255,0.22);
  border: 1px solid rgba(0,0,0,0.08);
  color: rgba(0,0,0,0.86);
}

/* Text */
.zq-body{
  position: relative;
  z-index: 2;

  font-size: 0.98rem;
  line-height: 1.45;
  color: rgba(0,0,0,0.86);
  margin-bottom: 10px;
}
.zq-meta{
  position: relative;
  z-index: 2;

  font-size: 0.86rem;
  color: rgba(0,0,0,0.60);
}

/* Accent mapping */
.zq-card[data-accent="warm"]   { --zq-accent: var(--zq-warm); }
.zq-card[data-accent="cool"]   { --zq-accent: var(--zq-cool); }
.zq-card[data-accent="mint"]   { --zq-accent: var(--zq-mint); }
.zq-card[data-accent="violet"] { --zq-accent: var(--zq-violet); }

/* Keep accent mainly on pill/icon */
.zq-card[data-accent] .zq-pill{
  background: rgba(var(--zq-accent), 0.10);
  border-color: rgba(var(--zq-accent), 0.20);
}
.zq-card[data-accent] .zq-icon{
  background: rgba(var(--zq-accent), 0.10);
  border-color: rgba(var(--zq-accent), 0.18);
  box-shadow: 0 16px 34px rgba(var(--zq-accent), 0.14);
}

/* =========================
   Dark mode (air-dark)
   ========================= */
html[data-theme="dark"] .zq-card{
  background: rgba(10, 12, 18, 0.38);
  border: 1px solid rgba(255,255,255,0.12);
  box-shadow:
    0 26px 80px rgba(0,0,0,0.62),
    0 1px 0 rgba(255,255,255,0.10) inset;

  backdrop-filter: blur(20px) saturate(150%);
  -webkit-backdrop-filter: blur(20px) saturate(150%);
}

html[data-theme="dark"] .zq-card::before{
  background: radial-gradient(1200px 260px at 30% 0%,
      rgba(255,255,255,0.22),
      rgba(255,255,255,0.06) 45%,
      rgba(255,255,255,0.00) 70%);
  opacity: 0.85;
}

html[data-theme="dark"] .zq-card::after{
  opacity: 0.50;
  background:
    radial-gradient(420px 260px at 18% 18%, rgba(var(--zq-accent), 0.20), rgba(0,0,0,0) 62%),
    radial-gradient(460px 300px at 88% 38%, rgba(var(--zq-accent), 0.12), rgba(0,0,0,0) 66%),
    radial-gradient(560px 360px at 50% 105%, rgba(0,0,0,0.30), rgba(0,0,0,0) 62%);
}

html[data-theme="dark"] .zq-card:hover{
  border-color: rgba(255,255,255,0.16);
  box-shadow:
    0 32px 96px rgba(0,0,0,0.72),
    0 1px 0 rgba(255,255,255,0.12) inset;
}

html[data-theme="dark"] .zq-body{ color: rgba(255,255,255,0.90); }
html[data-theme="dark"] .zq-meta{ color: rgba(255,255,255,0.66); }

html[data-theme="dark"] .zq-icon{
  background: rgba(255,255,255,0.06);
  border-color: rgba(255,255,255,0.12);
}

html[data-theme="dark"] .zq-pill{
  background: rgba(255,255,255,0.06);
  border-color: rgba(255,255,255,0.12);
  color: rgba(255,255,255,0.90);
}

html[data-theme="dark"] .zq-card[data-accent] .zq-pill{
  background: rgba(var(--zq-accent), 0.16);
  border-color: rgba(var(--zq-accent), 0.26);
}
html[data-theme="dark"] .zq-card[data-accent] .zq-icon{
  background: rgba(var(--zq-accent), 0.14);
  border-color: rgba(var(--zq-accent), 0.22);
  box-shadow: 0 18px 44px rgba(var(--zq-accent), 0.14);
}
</style>
