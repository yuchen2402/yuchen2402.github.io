---
layout: single
title: "Novels and Poetry 小說/詩歌"
permalink: /poetry/
author_profile: true
---

{% assign page.content = nil %}

<p style="color:#777; font-size:0.95em; margin-top:-10px; margin-bottom:25px;">
  Selected poems and lyrical writings exploring memory, emotion, and cultural identity.
</p>

{% for post in site.poetry %}
  {% include archive-single.html title=false %}
{% endfor %}
