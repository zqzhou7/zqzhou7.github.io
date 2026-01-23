---
layout: single
title: ""
permalink: /
author_profile: true
classes: wide
---

# Zhengquan Zhou  
### Environmental variability · benthic ecosystems · marine heatwaves

I study how **temporal structure of environmental extremes** shapes **benthic invertebrate performance and variability**, combining **mesocosm experiments**, **behavioural/physiological measurements**, and **mechanistic/statistical modelling**.

<div class="zq-grid">

  <div class="zq-card zq-card--warm">
    <div class="zq-card__top">
      <span class="zq-icon">🔥</span>
      <span class="zq-title">Marine heatwaves</span>
    </div>
    <div class="zq-body">
      How timing, duration, and variability of heat events reshape physiology and behaviour—beyond mean responses.
    </div>
    <div class="zq-meta">Focus: thermal profiles · response variance · predictability</div>
  </div>

  <div class="zq-card zq-card--cool">
    <div class="zq-card__top">
      <span class="zq-icon">⚙️</span>
      <span class="zq-title">Behaviour–sediment coupling</span>
    </div>
    <div class="zq-body">
      Quantifying bioturbation processes and feedbacks that control sediment stability on tidal flats.
    </div>
    <div class="zq-meta">Focus: mobility traits · mixing depth · sediment dynamics</div>
  </div>

  <div class="zq-card zq-card--mint">
    <div class="zq-card__top">
      <span class="zq-icon">📈</span>
      <span class="zq-title">Variability & thresholds</span>
    </div>
    <div class="zq-body">
      Linking environmental variance to biological variance using standardized metrics and breakpoint-aware models.
    </div>
    <div class="zq-meta">Focus: CV/TVI-style indices · outliers · two-slope patterns</div>
  </div>

  <div class="zq-card zq-card--violet">
    <div class="zq-card__top">
      <span class="zq-icon">🧰</span>
      <span class="zq-title">Reproducible workflows</span>
    </div>
    <div class="zq-body">
      Clean pipelines for experiments, visualization, and analysis—designed for traceability and re-use.
    </div>
    <div class="zq-meta">Focus: R/Python · GitHub · data templates · automation</div>
  </div>

</div>

<style>
/* --- Layout: force 2×2 on desktop, stack on mobile --- */
.zq-grid{
  display:grid;
  grid-template-columns: 1fr 1fr;   /* 2 columns */
  gap: 16px;
  margin-top: 18px;
}

/* --- Apple-ish card styling --- */
.zq-card{
  border-radius: 18px;
  padding: 18px 18px 16px 18px;
  background: #ffffff;
  border: 1px solid rgba(0,0,0,0.06);
  box-shadow:
    0 12px 30px rgba(0,0,0,0.06),
    0 1px 0 rgba(255,255,255,0.9) inset;
  transition: transform 140ms ease, box-shadow 140ms ease, border-color 140ms ease;
}

/* subtle “lift” on hover, like macOS UI */
.zq-card:hover{
  transform: translateY(-2px);
  box-shadow:
    0 18px 40px rgba(0,0,0,0.08),
    0 1px 0 rgba(255,255,255,0.9) inset;
  border-color: rgba(0,0,0,0.10);
}

.zq-card__top{
  display:flex;
  align-items:center;
  gap: 10px;
  margin-bottom: 10px;
}

.zq-icon{
  width: 34px;
  height: 34px;
  display:inline-flex;
  align-items:center;
  justify-content:center;
  border-radius: 12px;
  background: rgba(255,255,255,0.65);
  border: 1px solid rgba(0,0,0,0.06);
  font-size: 18px;
}

.zq-title{
  font-weight: 650;
  letter-spacing: 0.1px;
  font-size: 1.05rem;
}

.zq-body{
  font-size: 0.98rem;
  line-height: 1.45;
  color: rgba(0,0,0,0.78);
  margin-bottom: 10px;
}

.zq-meta{
  font-size: 0.86rem;
  color: rgba(0,0,0,0.55);
}

/* --- “Apple-ish” soft gradient tints per card --- */
.zq-card--warm{
  background: linear-gradient(135deg, rgba(255, 240, 230, 0.95), rgba(255,255,255,0.92));
}
.zq-card--cool{
  background: linear-gradient(135deg, rgba(230, 245, 255, 0.95), rgba(255,255,255,0.92));
}
.zq-card--mint{
  background: linear-gradient(135deg, rgba(232, 255, 246, 0.95), rgba(255,255,255,0.92));
}
.zq-card--violet{
  background: linear-gradient(135deg, rgba(242, 236, 255, 0.95), rgba(255,255,255,0.92));
}

/* --- Mobile: stack --- */
@media (max-width: 780px){
  .zq-grid{ grid-template-columns: 1fr; }
}
</style>
