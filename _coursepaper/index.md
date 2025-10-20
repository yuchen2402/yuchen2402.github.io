---
layout: archive
title: "Course Essays 課程論文"
permalink: /coursepaper/
author_profile: true
---

<div class="page__content" style="margin-bottom: 1.5em;">
  <p style="color:#777; font-size:0.95em; margin-top:-10px;">
    Essays written for coursework assessment during the MA programme.
  </p>
</div>

{% for post in site.coursepaper %}
  {% include archive-single.html title=false %}
{% endfor %}
