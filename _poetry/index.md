---
layout: default
title: "Novels and Poetry 小說/詩歌"
permalink: /poetry/
---

{% include sidebar.html %}  <!-- ✅ 头像回来了 -->

<div id="main" role="main">
  <div class="archive">
    <h1 class="page__title">{{ page.title }}</h1>

    <!-- ✅ 灰色说明，正确在标题下 -->
    <p style="color:#777; font-size:0.95em; margin-top:-10px; margin-bottom:25px;">
      Selected poems and lyrical writings exploring memory, emotion, and cultural identity.
    </p>

    {% for post in site.poetry %}
      {% include archive-single.html title=false %}
    {% endfor %}
  </div>
</div>
