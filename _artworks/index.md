---
layout: single
title: "Art Works 藝術作品"
permalink: /artworks/
author_profile: true
---

{% raw %}

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

<!-- ✅ 引入 Lightbox -->
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

/* 🔍 左下角放大细节窗口样式 */
.zoom-preview {
  position: fixed;
  bottom: 20px;
  left: 20px;
  width: 220px;
  height: 220px;
  border: 2px solid #aaa;
  background-repeat: no-repeat;
  background-size: 200%;
  display: none;
  z-index: 99999;
  box-shadow: 0 0 8px rgba(0,0,0,0.3);
  background-color: #fff;
}
</style>

<div class="zoom-preview" id="zoomPreview"></div>

<script>
document.addEventListener("DOMContentLoaded", function () {
  const zoomPreview = document.getElementById("zoomPreview");

  // 循环检测 lightbox 是否打开
  function attachZoom() {
    const lightboxImage = document.querySelector(".lb-image");
    if (lightboxImage && !lightboxImage.hasZoomHandler) {
      lightboxImage.hasZoomHandler = true;

      // 鼠标移动时更新细节视图
      lightboxImage.addEventListener("mousemove", function (event) {
        const rect = lightboxImage.getBoundingClientRect();
        const x = ((event.clientX - rect.left) / rect.width) * 100;
        const y = ((event.clientY - rect.top) / rect.height) * 100;
        zoomPreview.style.backgroundImage = `url('${lightboxImage.src}')`;
        zoomPreview.style.backgroundPosition = `${x}% ${y}%`;
        zoomPreview.style.display = "block";
      });

      // 鼠标离开隐藏
      lightboxImage.addEventListener("mouseleave", function () {
        zoomPreview.style.display = "none";
      });
    }
  }

  // 每 500ms 检查一次
  setInterval(attachZoom, 500);
});
</script>

  }

  // 定时检测 Lightbox 是否出现
  setInterval(attachZoom, 500);
});
</script>
{% endraw %}
