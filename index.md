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

  <div class="zq-card" data-accent="warm">
    <div class="zq-card__top">
      <span class="zq-icon" aria-hidden="true">🔥</span>
      <span class="zq-pill">Marine heatwaves</span>
    </div>
    <div class="zq-body">
      How timing, duration, and variability of heat events reshape physiology and behaviour—beyond mean responses.
    </div>
    <div class="zq-meta">Focus: thermal profiles · response variance · predictability</div>
  </div>

  <div class="zq-card" data-accent="cool">
    <div class="zq-card__top">
      <span class="zq-icon" aria-hidden="true">⚙️</span>
      <span class="zq-pill">Behaviour–sediment coupling</span>
    </div>
    <div class="zq-body">
      Quantifying bioturbation processes and feedbacks that control sediment stability on tidal flats.
    </div>
    <div class="zq-meta">Focus: mobility traits · mixing depth · sediment dynamics</div>
  </div>

  <div class="zq-card" data-accent="mint">
    <div class="zq-card__top">
      <span class="zq-icon" aria-hidden="true">📈</span>
      <span class="zq-pill">Variability &amp; thresholds</span>
    </div>
    <div class="zq-body">
      Linking environmental variance to biological variance using standardized metrics and breakpoint-aware models.
    </div>
    <div class="zq-meta">Focus: CV/TVI-style indices · outliers · two-slope patterns</div>
  </div>

  <div class="zq-card" data-accent="violet">
    <div class="zq-card__top">
      <span class="zq-icon" aria-hidden="true">🧰</span>
      <span class="zq-pill">Reproducible workflows</span>
    </div>
    <div class="zq-body">
      Clean pipelines for experiments, visualization, and analysis—designed for traceability and re-use.
    </div>
    <div class="zq-meta">Focus: R/Python · GitHub · data templates · automation</div>
  </div>

</div>

<style>
/* ===========================================
   ZQ Home Cards (Apple-glass, dark-toggle safe)
   Dark mode selector: html[data-theme="dark"]
   =========================================== */

/* --- Grid: 2×2 desktop, stack on mobile --- */
.zq-grid{
  display:grid;
  grid-template-columns: 1fr 1fr;
  gap: 16px;
  margin-top: 18px;
}
@media (max-width: 780px){
  .zq-grid{ grid-template-columns: 1fr; }
}

/* --- Accent tokens (only for pill + icon) --- */
:root{
  --zq-warm: 255, 122, 0;
  --zq-cool: 0, 122, 255;
  --zq-mint: 52, 199, 89;
  --zq-violet: 175, 82, 222;
}

/* --- Card base: neutral glass --- */
.zq-card{
  position: relative;
  overflow: hidden;
  border-radius: 18px;
  padding: 18px 18px 16px 18px;

  background: rgba(255,255,255,0.70);
  border: 1px solid rgba(0,0,0,0.08);
  box-shadow: 0 12px 30px rgba(0,0,0,0.08);

  backdrop-filter: blur(14px);
  -webkit-backdrop-filter: blur(14px);

  transition: transform 140ms ease, box-shadow 140ms ease, border-color 140ms ease;
}

/* Subtle “glass sheen” */
.zq-card::before{
  content:"";
  position:absolute;
  inset: 0;
  pointer-events:none;
  border-radius: 18px;
  background: linear-gradient(
    to bottom,
    rgba(255,255,255,0.45),
    rgba(255,255,255,0.00) 40%
  );
  opacity: 0.55;
}

.zq-card:hover{
  transform: translateY(-2px);
  box-shadow: 0 18px 40px rgba(0,0,0,0.10);
  border-color: rgba(0,0,0,0.12);
}

/* --- Top row --- */
.zq-card__top{
  display:flex;
  align-items:center;
  gap: 10px;
  margin-bottom: 10px;
}

/* --- Icon --- */
.zq-icon{
  width: 34px;
  height: 34px;
  display:inline-flex;
  align-items:center;
  justify-content:center;
  border-radius: 12px;

  background: rgba(255,255,255,0.50);
  border: 1px solid rgba(0,0,0,0.06);
  font-size: 18px;
}

/* --- Accent pill (the color lives here) --- */
.zq-pill{
  font-weight: 650;
  font-size: 0.95rem;
  letter-spacing: 0.1px;

  padding: 6px 10px;
  border-radius: 999px;

  background: rgba(255,255,255,0.55);
  border: 1px solid rgba(0,0,0,0.08);
  color: rgba(0,0,0,0.82);
}

/* --- Text --- */
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

/* --- Accent mapping --- */
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

/* ===========================================
   Dark mode (toggle button)
   html[data-theme="dark"]
   =========================================== */

html[data-theme="dark"] .zq-card{
  background: rgba(20, 20, 24, 0.62);
  border: 1px solid rgba(255,255,255,0.10);
  box-shadow: 0 18px 48px rgba(0,0,0,0.55);
}

html[data-theme="dark"] .zq-card::before{
  background: linear-gradient(
    to bottom,
    rgba(255,255,255,0.12),
    rgba(255,255,255,0.00) 40%
  );
  opacity: 0.45;
}

html[data-theme="dark"] .zq-card:hover{
  border-color: rgba(255,255,255,0.14);
  box-shadow: 0 22px 58px rgba(0,0,0,0.62);
}

html[data-theme="dark"] .zq-body{
  color: rgba(255,255,255,0.88);
}
html[data-theme="dark"] .zq-meta{
  color: rgba(255,255,255,0.62);
}

html[data-theme="dark"] .zq-icon{
  background: rgba(255,255,255,0.06);
  border-color: rgba(255,255,255,0.10);
}

html[data-theme="dark"] .zq-pill{
  background: rgba(255,255,255,0.06);
  border-color: rgba(255,255,255,0.12);
  color: rgba(255,255,255,0.88);
}

/* Keep accents subtle (not neon) in dark */
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
