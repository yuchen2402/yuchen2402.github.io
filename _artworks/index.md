---
layout: single
title: "Art Works 藝術作品"
permalink: /artworks/
author_profile: true
---

<p style="color:#777; font-size:0.95em; margin-top:-10px; margin-bottom:25px;">
  A selection of artworks and visual experiments created during the BA programme.
</p>

<div class="gallery">
  {% for work in site.artworks %}
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

<!-- 🔍 Hover zoom detail viewer -->
<style>
  .zoom-container {
    position: relative;
    display: inline-block;
    cursor: crosshair;
  }

  .zoom-lens {
    position: absolute;
    border: 1px solid #ccc;
    width: 100px;
    height: 100px;
    opacity: 0;
    transition: opacity 0.2s;
  }

  .zoom-result {
    position: fixed;
    bottom: 20px;
    left: 20px;
    width: 200px;
    height: 200px;
    border: 2px solid #888;
    background-repeat: no-repeat;
    background-size: 200%;
    display: none;
    z-index: 9999;
  }
</style>

<div class="zoom-result" id="zoomResult"></div>

<script>
  document.addEventListener("DOMContentLoaded", function() {
    const images = document.querySelectorAll(".gallery-item img");
    const zoomResult = document.getElementById("zoomResult");

    images.forEach(img => {
      const container = document.createElement("div");
      container.classList.add("zoom-container");
      img.parentNode.insertBefore(container, img);
      container.appendChild(img);

      container.addEventListener("mousemove", e => {
        zoomResult.style.display = "block";
        const rect = img.getBoundingClientRect();
        const x = e.clientX - rect.left;
        const y = e.clientY - rect.top;
        const xPercent = x / rect.width * 100;
        const yPercent = y / rect.height * 100;
        zoomResult.style.backgroundImage = `url(${img.src})`;
        zoomResult.style.backgroundPosition = `${xPercent}% ${yPercent}%`;
        zoomResult.style.opacity = 1;
      });

      container.addEventListener("mouseleave", () => {
        zoomResult.style.display = "none";
      });
    });
  });
</script>
