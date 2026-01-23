---
layout: single
title: ""
permalink: /
author_profile: true
classes: wide
---

# Zhengquan Zhou  
### Marine ecology & experimental biophysics of benthic systems

<div style="display:grid; grid-template-columns: repeat(auto-fit, minmax(240px, 1fr)); gap:14px; margin: 18px 0 10px 0;">

<div class="notice--primary" style="padding:16px; border-radius:14px;">
  <strong>🔥 Marine heatwaves</strong><br>
  How timing, duration, and variability shape physiological and behavioural outcomes.
</div>

<div class="notice--info" style="padding:16px; border-radius:14px;">
  <strong>⚙️ Behaviour–sediment coupling</strong><br>
  Quantifying bioturbation processes and feedbacks on tidal flats.
</div>

<div class="notice--success" style="padding:16px; border-radius:14px;">
  <strong>📈 Variability & predictability</strong><br>
  Linking environmental variance to response variance (CV/TVI-style metrics).
</div>

<div class="notice--warning" style="padding:16px; border-radius:14px;">
  <strong>🧰 Experiments + modelling</strong><br>
  Mesocosms, thermal profiles, trait variability, reproducible analysis pipelines.
</div>

</div>

<div style="display:flex; gap:12px; flex-wrap:wrap; margin: 10px 0 16px 0;">
  <a class="btn btn--primary" href="/about/">About</a>
  <a class="btn btn--success" href="/publications/">Publications</a>
  <a class="btn btn--info" href="/lab-notes/">Lab Notes</a>
  <a class="btn btn--inverse" href="/cv/">CV</a>
</div>

---

## Latest lab notes
{% assign labs = site.posts | where_exp: "post", "post.tags contains 'lab-notes'" %}
{% for post in labs limit:3 %}
- **[{{ post.title }}]({{ post.url }})** <small>({{ post.date | date: "%Y-%m-%d" }})</small>
{% endfor %}

<small>Tip: tag your posts with <code>lab-notes</code> to show up here.</small>
