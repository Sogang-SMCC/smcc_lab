---
layout: page
title: Pictures
permalink: /pictures/
description: Group Pictures
nav: true
nav_order: 4

# Same arrangement as the old site: a row with one photo is shown large and centered,
# photos in the same row share one height. r = width / height of the photo.
albums:
  - title: 2026 Summer @Sogang
    rows:
      - [{ f: 2026-06-26-14-15-49-001-1.jpg, r: 1.482 }]
      - [{ f: 2026-06-26-14-15-51-005.jpg, r: 1.332 }, { f: 2026-06-26-14-15-52-008.jpg, r: 1.335 }, { f: 2026-06-26-14-15-51-007.jpg, r: 1.332 }]
  - title: 2025 Spring @Sogang
    rows:
      - [{ f: img_7833.jpg, r: 1.504 }]
      - [{ f: img_7829.jpg, r: 1.509 }, { f: img_0380.jpg, r: 1.335 }]
      - [{ f: img_7809.jpg, r: 1.371 }, { f: img_7814-1.jpg, r: 0.884 }, { f: img_7818-1.jpg, r: 0.982 }]
  - title: 2024 Spring @Sogang
    rows:
      - [{ f: 2024-05-22-3.49.49.png, r: 1.768 }]
      - [{ f: 2024-05-22-3.50.57.png, r: 1.141 }, { f: 2024-05-22-3.51.33.png, r: 0.902 }]
  - title: 2023 Home-Coming Day
    rows:
      - [{ f: img_7837.jpg, r: 1.334 }]
  - title: 2023 Spring @Sogang
    rows:
      - [{ f: img_7518-1.jpg, r: 1.961 }]
      - [{ f: 2023-06-02-5.47.30.png, r: 0.672 }, { f: 2023-06-02-5.48.29.png, r: 1.578 }, { f: 2023-06-02-5.47.53.png, r: 0.68 }]
  - title: 2022년 졸업
    rows:
      - [{ f: img_5604.jpg, r: 1.333 }]
  - title: 2022 Spring @Sogang
    rows:
      - [{ f: img_7108.jpg, r: 1.503 }]
      - [{ f: img_7087.jpg, r: 1.504 }, { f: img_7101.jpg, r: 1.504 }]
      - [{ f: img_7103.jpg, r: 1.504 }, { f: img_7148.jpg, r: 1.504 }]
  - title: 2021 Spring @Sogang
    row_width: 75% # these photos are small; keep multi-photo rows narrower
    rows:
      - [{ f: 58b2b406-5d6e-4f03-8bff-c61bcacd2d9e.jpg, r: 1.5 }, { f: 62a1a20f-7aaa-4dd9-ab72-a226ff8527bb.jpg, r: 1.5 }]
      - [{ f: 7763f78a-ff4f-41c5-ad89-8e30592d0216.jpg, r: 1.504 }]
  - title: 2020 Spring @Sogang
    row_width: 75% # these photos are small; keep multi-photo rows narrower
    rows:
      - [{ f: unadjustednonraw_thumb_17533.jpg, r: 1.391 }]
      - [{ f: unadjustednonraw_thumb_17531.jpg, r: 1.5 }, { f: unadjustednonraw_thumb_17519.jpg, r: 1.5 }]
      - [{ f: unadjustednonraw_thumb_1752c.jpg, r: 1.5 }, { f: unadjustednonraw_thumb_1752d.jpg, r: 1.5 }]
---

{% include smcc_style.liquid %}

{% for album in page.albums %}

<h3 class="mt-5">{{ album.title }}</h3>
{% for row in album.rows %}
  <div class="smcc-photo-row{% if row.size == 1 %} smcc-photo-big{% endif %}"{% if row.size > 1 and album.row_width %} style="width: {{ album.row_width }}; margin-left: auto; margin-right: auto;"{% endif %}>
    {% for photo in row %}
      <div style="flex: {{ photo.r }} 1 0;">
        {% assign path = 'assets/img/smcc/pictures/' | append: photo.f %}
        {% include figure.liquid path=path class="img-fluid rounded z-depth-1" alt=album.title zoomable=true %}
      </div>
    {% endfor %}
  </div>
{% endfor %}
{% endfor %}
