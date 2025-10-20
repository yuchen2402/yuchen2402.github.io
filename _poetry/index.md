---
layout: single
title: "Novels and Poetry 小說/詩歌"
permalink: /poetry/
author_profile: true
---

<div class="page__content" style="margin-bottom: 1.5em;">
  <p style="color:#777; font-size:0.95em; margin-top:-10px;">
    Selected poems and lyrical writings exploring memory, emotion, and cultural identity.
  </p>
</div>

{% for post in site.poetry %}
  {% include archive-single.html title=false %}
{% endfor %}
