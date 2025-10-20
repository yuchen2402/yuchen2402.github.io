---
layout: default
title: "Novels and Poetry 小說/詩歌"
permalink: /poetry/
author_profile: true
---

<div id="main" role="main">
  {% include sidebar.html %}

  <div class="archive">
    <h1 class="page__title">{{ page.title }}</h1>

    <!-- ✅ 灰色说明，现在一定出现在标题下方 -->
    <p style="color:#777; font-size:0.95em; margin-top:-10px; margin-bottom:25px;">
      Selected poems and lyrical writings exploring memory, emotion, and cultural identity.
    </p>

    {% for post in site.poetry %}
      {% include archive-single.html title=false %}
    {% endfor %}
  </div>
</div>
