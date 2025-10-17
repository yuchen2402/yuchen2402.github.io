---
layout: archive
title: "Critical Essays 學術隨筆"
permalink: /criticalessays/
author_profile: true
---

<p style="color:#777; font-size:0.95em; margin-top:-10px;">
Independent reflections and essays on film and literature beyond formal coursework.
</p>

{% include base_path %}

{% for post in site.criticalessays %}
  {% include archive-single.html title=false %}
{% endfor %}
