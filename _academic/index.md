---
layout: single
title: "Art Works 藝術作品"
permalink: /academic/
author_profile: true
---

{% assign page.content = nil %}

<p style="color:#777; font-size:0.95em; margin-top:-10px; margin-bottom:25px;">
  A selection of artworks and visual experiments created during the MA programme.
</p>

<div class="gallery" style="display:flex; flex-wrap:wrap; gap:20px; margin-top:20px;">
  {% for work in site.academic %}
    {% if work.image %}
      <div style="width:30%; text-align:center;">
        <img src="{{ work.image }}" alt="{{ work.title }}" style="width:100%; border-radius:10px; box-shadow:0 2px 8px rgba(0,0,0,0.15);">
        <p style="font-size:0.9em; color:#555; margin-top:8px;">{{ work.caption | default: work.title }}</p>
      </div>
    {% endif %}
  {% endfor %}
</div>
