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
   ZQ Home Cards — Air-glass (less white), glossy, dark-toggle safe
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

/* Accent tokens */
:root{
  --zq-warm: 255, 122, 0;    /* iOS orange */
  --zq-cool: 0, 122, 255;    /* iOS blue */
  --zq-mint: 52, 199, 89;    /* iOS green */
  --zq-violet: 175, 82, 222; /* iOS purple */
}

/* Accent mapping */
.zq-card[data-accent="warm"]   { --zq-accent: var(--zq-warm); }
.zq-card[data-accent="cool"]   { --zq-accent: var(--zq-cool); }
.zq-card[data-accent="mint"]   { --zq-accent: var(--zq-mint); }
.zq-card[data-accent="violet"] { --zq-accent: var(--zq-violet); }

/* --- Card base: airy glass (NOT white) --- */
.zq-card{
  position: relative;
  overflow: hidden;
  border-radius: 20px;
  padding: 18px 18px 16px 18px;

  /* Air-light glass: slightly tinted + translucent */
  background:
    linear-gradient(180deg,
      rgba(255,255,255,0.62),
      rgba(255,255,255,0.40)
    );

  border: 1px solid rgba(0,0,0,0.06);

  /* Apple-ish depth: soft but present */
  box-shadow:
    0 20px 50px rgba(0,0,0,0.08),
    0 1px 0 rgba(255,255,255,0.70) inset;

  backdrop-filter: blur(18px) saturate(130%);
  -webkit-backdrop-filter: blur(18px) saturate(130%);

  transition: transform 160ms ease, box-shadow 160ms ease, border-color 160ms ease;
}

/* Accent aura (subtle glow behind the card) */
.zq-card::after{
  content:"";
  position:absolute;
  inset:-40px;
  pointer-events:none;
  background:
    radial-gradient(600px 220px at 15% 0%,
      rgba(var(--zq-accent), 0.18),
      rgba(var(--zq-accent), 0.00) 60%
    ),
    radial-gradient(420px 220px at 85% 110%,
      rgba(var(--zq-accent), 0.10),
      rgba(var(--zq-accent), 0.00) 60%
    );
  opacity: 0.85;
  filter: blur(12px);
}

/* Glass sheen (top highlight) */
.zq-card::before{
  content:"";
  position:absolute;
  inset:0;
  pointer-events:none;
  border-radius: 20px;
  background:
    linear-gradient(to bottom,
      rgba(255,255,255,0.55),
      rgba(255,255,255,0.00) 42%
    );
  opacity: 0.60;
}

.zq-card:hover{
  transform: translateY(-2px);
  border-color: rgba(0,0,0,0.10);
  box-shadow:
    0 26px 70px rgba(0,0,0,0.10),
    0 1px 0 rgba(255,255,255,0.75) inset;
}

/* --- Top row --- */
.zq-card__top{
  display:flex;
  align-items:center;
  gap: 10px;
  margin-bottom: 10px;
  position: relative;
  z-index: 1;
}

/* Icon: small glass tile */
.zq-icon{
  width: 34px;
  height: 34px;
  display:inline-flex;
  align-items:center;
  justify-content:center;
  border-radius: 12px;

  background: rgba(255,255,255,0.35);
  border: 1px solid rgba(0,0,0,0.06);

  box-shadow:
    0 10px 22px rgba(var(--zq-accent), 0.14);

  font-size: 18px;
}

/* Pill: clean accent label */
.zq-pill{
  font-weight: 650;
  font-size: 0.95rem;
  letter-spacing: 0.1px;

  padding: 6px 10px;
  border-radius: 999px;

  background: rgba(var(--zq-accent), 0.10);
  border: 1px solid rgba(var(--zq-accent), 0.22);

  color: rgba(0,0,0,0.82);
}

/* Text */
.zq-body, .zq-meta{
  position: relative;
  z-index: 1;
}
.zq-body{
  font-size: 0.98rem;
  line-height: 1.45;
  color: rgba(0,0,0,0.82);
  margin-bottom: 10px;
}
.zq-meta{
  font-size: 0.86rem;
  color: rgba(0,0,0,0.58);
}

/* ===========================================
   Dark mode
   =========================================== */

html[data-theme="dark"] .zq-card{
  background:
    linear-gradient(180deg,
      rgba(22,22,26,0.65),
      rgba(18,18,22,0.45)
    );
  border: 1px solid rgba(255,255,255,0.10);
  box-shadow:
    0 26px 70px rgba(0,0,0,0.62),
    0 1px 0 rgba(255,255,255,0.06) inset;
}

html[data-theme="dark"] .zq-card::before{
  background: linear-gradient(
    to bottom,
    rgba(255,255,255,0.14),
    rgba(255,255,255,0.00) 45%
  );
  opacity: 0.55;
}

html[data-theme="dark"] .zq-card::after{
  opacity: 0.70;
  filter: blur(14px);
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
  box-shadow: 0 14px 30px rgba(var(--zq-accent), 0.14);
}

html[data-theme="dark"] .zq-pill{
  background: rgba(var(--zq-accent), 0.16);
  border-color: rgba(var(--zq-accent), 0.26);
  color: rgba(255,255,255,0.90);
}
</style>
