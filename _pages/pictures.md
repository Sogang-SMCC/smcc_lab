---
layout: page
title: Pictures
permalink: /pictures/
description: Group Pictures
nav: true
nav_order: 4

albums:
  - title: 2026 Summer @Sogang
    photos: [2026-06-26-14-15-49-001-1.jpg, 2026-06-26-14-15-51-005.jpg, 2026-06-26-14-15-52-008.jpg, 2026-06-26-14-15-51-007.jpg]
  - title: 2025 Spring @Sogang
    photos: [img_7833.jpg, img_7829.jpg, img_0380.jpg, img_7809.jpg, img_7814-1.jpg, img_7818-1.jpg]
  - title: 2024 Spring @Sogang
    photos: [2024-05-22-3.49.49.jpg, 2024-05-22-3.50.57.jpg, 2024-05-22-3.51.33.jpg]
  - title: 2023 Home-Coming Day
    photos: [img_7837.jpg]
  - title: 2023 Spring @Sogang
    photos: [img_7518-1.jpg, 2023-06-02-5.47.30.jpg, 2023-06-02-5.48.29.jpg, 2023-06-02-5.47.53.jpg]
  - title: 2022년 졸업
    photos: [img_5604.jpg]
  - title: 2022 Spring @Sogang
    photos: [img_7108.jpg, img_7087.jpg, img_7101.jpg, img_7103.jpg, img_7148.jpg]
  - title: 2021 Spring @Sogang
    photos: [58b2b406-5d6e-4f03-8bff-c61bcacd2d9e.jpg, 62a1a20f-7aaa-4dd9-ab72-a226ff8527bb.jpg, 7763f78a-ff4f-41c5-ad89-8e30592d0216.jpg]
  - title: 2020 Spring @Sogang
    photos:
      [
        unadjustednonraw_thumb_17533.jpg,
        unadjustednonraw_thumb_17531.jpg,
        unadjustednonraw_thumb_17519.jpg,
        unadjustednonraw_thumb_1752c.jpg,
        unadjustednonraw_thumb_1752d.jpg,
      ]
---

{% for album in page.albums %}

<h3 class="mt-4">{{ album.title }}</h3>
<div class="row">
  {% for photo in album.photos %}
    <div class="col-sm-6 col-md-4 mt-3">
      {% assign path = 'assets/img/smcc/pictures/' | append: photo %}
      {% include figure.liquid path=path class="img-fluid rounded z-depth-1" alt=album.title zoomable=true %}
    </div>
  {% endfor %}
</div>
{% endfor %}
