---
layout: about
title: Welcome
permalink: /
subtitle: Department of Chemistry, <a href='https://www.sogang.ac.kr/'>Sogang University</a> · 서강대학교 화학과

selected_papers: false # rendered below with our own heading
social: false

announcements:
  enabled: false

latest_posts:
  enabled: false
---

<style>
  .post-title {
    font-weight: 700;
  }
</style>

<div class="row">
  <div class="col-md-6">
    {% include figure.liquid path="assets/img/smcc/campus.jpg" class="img-fluid rounded z-depth-1" alt="Sogang University" %}
  </div>
  <div class="col-md-6 mt-3 mt-md-0">
    <p><strong>Soft Matter Computational Chemistry Lab</strong><br>
    Ricci Science Hall 1217, 1215<br>
    Department of Chemistry, Sogang University<br>
    Seoul 04107, Korea<br>
    TEL: 82-2-716-8889<br>
    e-mail: <a href="mailto:bjsung@sogang.ac.kr">bjsung@sogang.ac.kr</a></p>
    <p>서강대학교 화학과 리치과학관 1217호, 1215호<br>
    서울특별시 마포구 백범로 35<br>
    전화: 02-716-8889<br>
    이메일: <a href="mailto:bjsung@sogang.ac.kr">bjsung@sogang.ac.kr</a></p>
  </div>
</div>

#### Molecular Simulations at multiscales

"연성 소재 전산화학 연구실"은 컴퓨터 시뮬레이션, 인공지능, 통계열역학, 양자화학을 포함한 여러가지 이론적 방법을 이용하여 재료물리화학, 생물물리화학 등 다양한 분야를 연구하고 있다.
자세한 내용은 [Research]({{ '/research/' | relative_url }}) 페이지를 참고하세요.

<h2 class="mt-5 pt-3">
  <a href="{{ '/publications/' | relative_url }}" style="color: inherit; font-weight: 400">Selected Publications</a>
</h2>

{% include smcc_pub_style.liquid %}
{% include selected_papers.liquid %}
