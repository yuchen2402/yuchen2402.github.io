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

<!-- 图片画廊 -->
<div class="gallery">
  {% for work in site.academic %}
    {% if work.image %}
      <div class="gallery-item">
        <a href="{{ work.image }}" data-lightbox="art-gallery" data-title="{{ work.caption | default: work.title }}">
          <img src="{{ work.image }}" alt="{{ work.title }}">
        </a>
        <p class="caption">{{ work.caption | default: work.title }}</p>
      </div>
    {% endif %}
  {% endfor %}
</div>

<!-- 引入 Lightbox2 -->
<link href="https://cdnjs.cloudflare.com/ajax/libs/lightbox2/2.11.3/css/lightbox.min.css" rel="stylesheet" />
<script src="https://cdnjs.cloudflare.com/ajax/libs/lightbox2/2.11.3/js/lightbox.min.js"></script>

<style>
.gallery {
  display: flex;
  flex-wrap: wrap;
  justify-content: flex-start;
  gap: 20px;
  margin-top: 25px;
}

.gallery-item {
  width: 30%;
  text-align: center;
}

.gallery-item img {
  width: 100%;
  border-radius: 10px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.15);
  transition: transform 0.2s ease;
}

.gallery-item img:hover {
  transform: scale(1.03);
}

.caption {
  font-size: 0.9em;
  color: #555;
  margin-top: 8px;
}
</style>
