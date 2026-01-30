---
layout: single
title: ""
permalink: /
author_profile: true
classes: wide
---

# Featured research themes

Exploring how **the temporal structure of environmental extremes** shapes **benthic invertebrate performance and variability**, integrating **experiments**, **physiological measurements**, and **statistical modelling**. 

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

  <a class="zq-card zq-card-link" data-accent="mint" href="https://doi.org/10.1016/j.gecco.2025.e03918" target="_blank" rel="noopener" aria-label="Variability & thresholds (opens in new tab)">
    <div class="zq-card__top">
      <span class="zq-icon" aria-hidden="true">📈</span>
      <span class="zq-pill">Variability &amp; thresholds</span>
    </div>
    <div class="zq-body">
      Exploring how environmental stress intensity and temporal structure shape variability, resilience, and nonlinear responses in marine organisms.
    </div>
    <div class="zq-meta">
      Focus: response heterogeneity · tipping points · performance stability under extremes
    </div>
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
/* ===========================================
   ZQ Home Cards (Apple-glass, air-theme friendly)
   Dark mode selector: html[data-theme="dark"]
   =========================================== */

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

/* Accent tokens */
:root{
  --zq-warm: 255, 122, 0;
  --zq-cool: 0, 122, 255;
  --zq-mint: 52, 199, 89;
  --zq-violet: 175, 82, 222;
}

/* Card base */
.zq-card{
  position: relative;
  overflow: hidden;
  border-radius: 20px;
  padding: 20px 20px 18px 20px;

  background: linear-gradient(
    180deg,
    rgba(255,255,255,0.75),
    rgba(255,255,255,0.55)
  ) !important;

  border: 1px solid rgba(255,255,255,0.45);

  box-shadow:
    0 12px 28px rgba(0,0,0,0.12),
    inset 0 1px 0 rgba(255,255,255,0.6);

  backdrop-filter: blur(22px) saturate(160%);
  -webkit-backdrop-filter: blur(22px) saturate(160%);

  transition: transform 160ms ease, box-shadow 160ms ease;
}

/* Glass sheen */
.zq-card::before{
  content:"";
  position:absolute;
  inset:0;
  pointer-events:none;
  border-radius:20px;

  background:
    radial-gradient(
      120% 60% at 10% 0%,
      rgba(255,255,255,0.75),
      rgba(255,255,255,0.0) 60%
    );

  opacity:0.6;
}

.zq-card:hover{
  transform: translateY(-4px);
  box-shadow:
    0 26px 70px rgba(0,0,0,0.18),
    inset 0 1px 0 rgba(255,255,255,0.7);
}

/* Make entire card clickable, remove underline everywhere */
.zq-card-link{
  display:block;
  text-decoration: none !important;
}
.zq-card-link *{
  text-decoration: none !important;
}
.zq-card-link:focus{
  outline: none;
}
.zq-card-link:focus-visible{
  outline: 3px solid rgba(0,122,255,0.35);
  outline-offset: 4px;
  border-radius: 20px;
}

/* Top row */
.zq-card__top{
  display:flex;
  align-items:center;
  gap: 10px;
  margin-bottom: 10px;
}

/* Icon */
.zq-icon{
  width: 34px;
  height: 34px;
  display:inline-flex;
  align-items:center;
  justify-content:center;
  border-radius: 12px;

  background: rgba(255,255,255,0.42);
  border: 1px solid rgba(0,0,0,0.06);
  font-size: 18px;
}

/* Accent pill */
.zq-pill{
  font-weight: 650;
  font-size: 0.95rem;
  letter-spacing: 0.1px;

  padding: 6px 10px;
  border-radius: 999px;

  background: rgba(255,255,255,0.45);
  border: 1px solid rgba(0,0,0,0.08);
  color: rgba(0,0,0,0.82);
}

/* Text */
.zq-body{
  font-size: 0.98rem;
  line-height: 1.45;
  color: rgba(0,0,0,0.82);
  margin-bottom: 10px;
}
.zq-meta{
  font-size: 0.86rem;
  color: rgba(0,0,0,0.56);
}

/* Accent mapping */
.zq-card[data-accent="warm"]   { --zq-accent: var(--zq-warm); }
.zq-card[data-accent="cool"]   { --zq-accent: var(--zq-cool); }
.zq-card[data-accent="mint"]   { --zq-accent: var(--zq-mint); }
.zq-card[data-accent="violet"] { --zq-accent: var(--zq-violet); }

/* Subtle accent styling */
.zq-card[data-accent] .zq-pill{
  background: rgba(var(--zq-accent), 0.10);
  border-color: rgba(var(--zq-accent), 0.22);
}
.zq-card[data-accent] .zq-icon{
  background: rgba(var(--zq-accent), 0.10);
  border-color: rgba(var(--zq-accent), 0.18);
  box-shadow: 0 10px 22px rgba(var(--zq-accent), 0.12);
}

/* Dark mode */
html[data-theme="dark"] .zq-card{
  background: linear-gradient(
    180deg,
    rgba(28,28,34,0.78),
    rgba(18,18,22,0.62)
  ) !important;

  border: 1px solid rgba(255,255,255,0.14);

  box-shadow:
    0 22px 60px rgba(0,0,0,0.65),
    inset 0 1px 0 rgba(255,255,255,0.12);

  backdrop-filter: blur(26px) saturate(140%);
}
html[data-theme="dark"] .zq-card::before{
  background: linear-gradient(
    to bottom,
    rgba(255,255,255,0.12),
    rgba(255,255,255,0.00) 42%
  );
  opacity: 0.45;
}
html[data-theme="dark"] .zq-body{ color: rgba(255,255,255,0.90); }
html[data-theme="dark"] .zq-meta{ color: rgba(255,255,255,0.64); }
html[data-theme="dark"] .zq-icon{
  background: rgba(255,255,255,0.06);
  border-color: rgba(255,255,255,0.10);
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
  box-shadow: 0 14px 30px rgba(var(--zq-accent), 0.14);
}
</style>
