---
layout: single
title: ""
permalink: /
author_profile: true
classes: wide
---

# Zhengquan Zhou, PhD  

I study how **temporal structure of environmental extremes** shapes **benthic invertebrate performance and variability**, combining **mesocosm experiments**, **behavioural/physiological measurements**, and **mechanistic/statistical modelling**.

<div class="zq-grid">

  <!-- Marine heatwaves -->
  <a href="https://doi.org/10.1002/lno.12332" class="zq-card-link" target="_blank">
    <div class="zq-card" data-accent="warm">
      <div class="zq-card__top">
        <span class="zq-icon">🔥</span>
        <span class="zq-pill">Marine heatwaves</span>
      </div>
      <div class="zq-body">
        How timing, duration, and variability of heat events reshape physiology and behaviour — beyond mean responses.
      </div>
      <div class="zq-meta">
        Focus: thermal profiles · response variance · predictability
      </div>
    </div>
  </a>

  <!-- Behaviour–sediment coupling -->
  <a href="https://doi.org/10.1002/lno.12669" class="zq-card-link" target="_blank">
    <div class="zq-card" data-accent="cool">
      <div class="zq-card__top">
        <span class="zq-icon">⚙️</span>
        <span class="zq-pill">Behaviour–sediment coupling</span>
      </div>
      <div class="zq-body">
        Quantifying bioturbation processes and feedbacks that control sediment stability on tidal flats.
      </div>
      <div class="zq-meta">
        Focus: mobility traits · mixing depth · sediment dynamics
      </div>
    </div>
  </a>

  <!-- Variability & thresholds -->
  <a href="https://doi.org/10.1016/j.gecco.2025.e03918" class="zq-card-link" target="_blank">
    <div class="zq-card" data-accent="mint">
      <div class="zq-card__top">
        <span class="zq-icon">📈</span>
        <span class="zq-pill">Variability &amp; thresholds</span>
      </div>
      <div class="zq-body">
        Linking environmental variance to biological variance using standardized metrics and breakpoint-aware models.
      </div>
      <div class="zq-meta">
        Focus: CV/TVI-style indices · outliers · two-slope patterns
      </div>
    </div>
  </a>

  <!-- Reproducible workflows -->
  <a href="https://github.com/zqzhou7" class="zq-card-link" target="_blank">
    <div class="zq-card" data-accent="violet">
      <div class="zq-card__top">
        <span class="zq-icon">🧰</span>
        <span class="zq-pill">Reproducible workflows</span>
      </div>
      <div class="zq-body">
        Clean pipelines for experiments, visualization, and analysis — designed for traceability and re-use.
      </div>
      <div class="zq-meta">
        Focus: R/Python · GitHub · data templates · automation
      </div>
    </div>
  </a>

</div>

<style>

/* ===============================
   Grid layout
   =============================== */

.zq-grid{
  display:grid;
  grid-template-columns: 1fr 1fr;
  gap: 18px;
  margin-top: 20px;
}

@media (max-width: 780px){
  .zq-grid{
    grid-template-columns: 1fr;
  }
}

/* ===============================
   Accent colors
   =============================== */

:root{
  --zq-warm: 255, 90, 0;
  --zq-cool: 0, 120, 255;
  --zq-mint: 52, 199, 89;
  --zq-violet: 175, 82, 222;
}

/* ===============================
   Card link wrapper
   =============================== */

.zq-card-link{
  text-decoration:none;
  color:inherit;
  display:block;
}

/* ===============================
   Glass card base
   =============================== */

.zq-card{
  position: relative;
  overflow: hidden;
  border-radius: 20px;
  padding: 20px;

  background: rgba(255,255,255,0.68);
  border: 1px solid rgba(0,0,0,0.08);
  box-shadow: 0 18px 40px rgba(0,0,0,0.10);

  backdrop-filter: blur(14px);
  -webkit-backdrop-filter: blur(14px);

  transition: transform .18s ease, box-shadow .18s ease;
}

/* Soft glossy sheen */
.zq-card::before{
  content:"";
  position:absolute;
  inset:0;
  border-radius:20px;
  background: linear-gradient(
    to bottom,
    rgba(255,255,255,0.45),
    rgba(255,255,255,0.00) 40%
  );
  opacity: .55;
  pointer-events:none;
}

.zq-card-link:hover .zq-card{
  transform: translateY(-3px) scale(1.01);
  box-shadow: 0 24px 60px rgba(0,0,0,0.14);
}

/* ===============================
   Card content
   =============================== */

.zq-card__top{
  display:flex;
  align-items:center;
  gap:10px;
  margin-bottom:12px;
}

.zq-icon{
  width:34px;
  height:34px;
  display:flex;
  align-items:center;
  justify-content:center;
  border-radius:12px;
  font-size:18px;
}

.zq-pill{
  font-weight:600;
  font-size:.95rem;
  padding:6px 12px;
  border-radius:999px;
}

.zq-body{
  font-size:.98rem;
  line-height:1.5;
  margin-bottom:10px;
}

.zq-meta{
  font-size:.85rem;
  opacity:.6;
}

/* ===============================
   Accent mapping
   =============================== */

.zq-card[data-accent="warm"]{ --zq-accent: var(--zq-warm); }
.zq-card[data-accent="cool"]{ --zq-accent: var(--zq-cool); }
.zq-card[data-accent="mint"]{ --zq-accent: var(--zq-mint); }
.zq-card[data-accent="violet"]{ --zq-accent: var(--zq-violet); }

.zq-card[data-accent] .zq-pill{
  background: rgba(var(--zq-accent), .12);
  border: 1px solid rgba(var(--zq-accent), .28);
}

.zq-card[data-accent] .zq-icon{
  background: rgba(var(--zq-accent), .12);
  border: 1px solid rgba(var(--zq-accent), .25);
  box-shadow: 0 10px 24px rgba(var(--zq-accent), .16);
}

/* ===============================
   Dark mode
   =============================== */

html[data-theme="dark"] .zq-card{
  background: rgba(18,18,22,.65);
  border:1px solid rgba(255,255,255,.12);
  box-shadow:0 22px 60px rgba(0,0,0,.6);
}

html[data-theme="dark"] .zq-body{
  color:rgba(255,255,255,.88);
}

html[data-theme="dark"] .zq-meta{
  color:rgba(255,255,255,.6);
}

html[data-theme="dark"] .zq-pill{
  color:#fff;
  background:rgba(255,255,255,.06);
}

html[data-theme="dark"] .zq-icon{
  background:rgba(255,255,255,.06);
}

html[data-theme="dark"] .zq-card[data-accent] .zq-pill{
  background: rgba(var(--zq-accent), .18);
}

html[data-theme="dark"] .zq-card[data-accent] .zq-icon{
  background: rgba(var(--zq-accent), .16);
  box-shadow: 0 14px 34px rgba(var(--zq-accent), .18);
}

</style>
