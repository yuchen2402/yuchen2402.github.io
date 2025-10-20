---
layout: single
title: "Course Essays 課程論文"
permalink: /coursepaper/
author_profile: true
---

<!-- ✅ 灰色说明：位于标题下方 -->
<p style="color:#777; font-size:0.95em; margin-top:-10px; margin-bottom:25px;">
  Essays written for coursework assessment during the MA programme.
</p>

<!-- ✅ 循环部分 -->
{% for post in site.coursepaper %}
  {% include archive-single.html title=false %}
{% endfor %}
