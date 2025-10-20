---
layout: archive
title: "Novels and Poetry 小說/詩歌"
permalink: /poetry/
author_profile: true
collection_name: poetry
---

<div class="page__intro" style="margin-bottom:1.5em;">
  <p style="color:#777; font-size:0.95em; margin-top:-10px;">
    Selected poems and lyrical writings exploring memory, emotion, and cultural identity.
  </p>
</div>

{% include base_path %}

{% assign collection_name = page.collection | default: page.collection_name | default: 'posts' %}
{% for post in site[collection_name] %}
  {% include archive-single.html title=false %}
{% endfor %}
