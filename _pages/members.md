---
layout: page
title: Members
permalink: /members/
nav: true
nav_order: 1
---

{% include smcc_style.liquid %}

<style>
  .member-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(150px, 1fr)); gap: 1.5rem 1rem; margin: 1rem 0 2.5rem; }
  .member-card { text-align: center; font-size: 0.85rem; line-height: 1.4; }
  .member-card img { width: 100%; aspect-ratio: 3 / 4; object-fit: cover; border-radius: 6px; margin-bottom: 0.5rem; }
  .member-card .name { font-weight: 600; font-size: 0.95rem; }
  .member-card .email { word-break: break-all; }
  .member-pi { display: flex; gap: 1.5rem; align-items: center; flex-wrap: wrap; margin: 1rem 0 2.5rem; }
  .member-pi img { width: 260px; max-width: 100%; border-radius: 6px; }
  .member-pi .name { font-size: 1.2rem; font-weight: 600; }
  .member-group { font-size: 1.25rem; margin-top: 1.5rem; }
</style>

{% assign m = site.data.members %}
{% assign img_base = '/assets/img/smcc/members/' | relative_url %}

<div class="member-pi">
  <a href="{{ m.pi.url | relative_url }}"><img src="{{ img_base }}{{ m.pi.photo }}" alt="{{ m.pi.name_en }}"></a>
  <div>
    <div class="name">{{ m.pi.name }}</div>
    <div>{{ m.pi.name_en }}</div>
    <div><a href="mailto:{{ m.pi.email }}">{{ m.pi.email }}</a></div>
    <div class="mt-2"><small>(자세한 정보를 원하시면 사진을 클릭하세요)<br>(For more information, click on the figure)</small></div>
  </div>
</div>

{% for section in m.current %}
{% if forloop.first %}<h2>Current Members</h2>{% endif %}
  <h3 class="member-group">{{ section.title }}</h3>
  <div class="member-grid">
    {% for p in section.people %}
      <div class="member-card">
        <img src="{{ img_base }}{{ p.photo }}" alt="{{ p.name }}" loading="lazy">
        <div class="name">{{ p.name }}</div>
        <div class="email">{{ p.email }}</div>
      </div>
    {% endfor %}
  </div>
{% endfor %}

{% for section in m.alumni %}
{% if forloop.first %}<h2>Alumni</h2>{% endif %}
  <h3 class="member-group">{{ section.title }}</h3>
  <div class="member-grid">
    {% for p in section.people %}
      <div class="member-card">
        <img src="{{ img_base }}{{ p.photo }}" alt="{{ p.name }}" loading="lazy">
        <div class="name">{{ p.name }}</div>
        <div class="email">{{ p.email }}</div>
        {% for line in p.info %}<div>{{ line }}</div>{% endfor %}
      </div>
    {% endfor %}
  </div>
{% endfor %}
