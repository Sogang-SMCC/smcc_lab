---
layout: page
title: 성봉준 (Bong June Sung)
permalink: /members/bong-june/
description: Professor, Department of Chemistry, Sogang University
nav: false
---

<style>
  /* Photo on the left, Name~Career on the right with top and bottom edges level, as on the old site */
  .prof-top {
    display: flex;
    align-items: stretch;
    margin-bottom: 2.5rem;
  }
  .prof-top .prof-photo {
    flex: 0 0 auto;
  }
  .prof-top .prof-photo img {
    display: block;
    height: 230px;
    width: auto;
  }
  .prof-info {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    margin-left: 2rem;
    font-size: 15px;
    line-height: 1.6;
  }
  .prof-info p,
  .prof-info ul {
    margin: 0;
  }
  .prof-info h5 {
    font-size: 1.05rem;
    margin: 0 0 0.15rem;
  }
  @media (max-width: 767px) {
    .prof-top {
      flex-direction: column;
    }
    .prof-info {
      margin: 1rem 0 0;
    }
    .prof-top .prof-photo img {
      height: auto;
      width: 100%;
      max-width: 320px;
      max-height: none;
    }
    .prof-info > * + * {
      margin-top: 0.75rem;
    }
  }
  /* Contact follows right below; Awards, Research Interests, Selected Publications are separate blocks */
  article h4 {
    margin-top: 1rem;
  }
  article h4.prof-block {
    margin-top: 4rem;
  }
</style>

<div class="prof-top">
  <div class="prof-photo">
    <img class="z-depth-1 rounded" src="{{ '/assets/img/smcc/members/prof_sung.png' | relative_url }}" alt="Prof. Bong June Sung">
  </div>
  <div class="prof-info">
    <p><strong>Name:</strong> 성봉준 (Bong June Sung)<br>
    <strong>Major:</strong> 물리화학 (Physical Chemistry)</p>
    <div>
      <h5>Education</h5>
      <ul>
        <li>B. S. — Seoul National University (1999)</li>
        <li>M. S. — Seoul National University (2001)</li>
        <li>Ph. D. — University of Wisconsin-Madison (2006)</li>
      </ul>
    </div>
    <div>
      <h5>Career</h5>
      <ul>
        <li>2006 ~ 2007: Post-Doc at UW-Madison</li>
        <li>2007 ~ Current: Professor at Sogang University, Chemistry</li>
      </ul>
    </div>
  </div>
</div>

#### Contact

- Telephone: 82-2-705-8880
- E-mail: [bjsung@sogang.ac.kr](mailto:bjsung@sogang.ac.kr)
- Office: 리치과학관 1217호 (Ricci Science Hall 1217)

<h4 class="prof-block">Awards</h4>

1. 신국조 학술상, 대한화학회 물리화학분과회, 2023/5
2. 젊은물리화학자상, 대한화학회 물리화학분과회, 2019/10
3. [KCS-Wiley Young Chemist Award 2014](http://www.chemistryviews.org/details/ezine/6836381/KCS-Wiley_Young_Chemist_Award_2014.html), 2014/10
4. The Distinguished Lectureship Award, The Chemical Society of Japan, 2011/03
5. 서강대학교 자연과학부 Teaching Excellence Award, 2014
6. 서강대학교 자연과학부 Teaching Excellence Award, 2015
7. 서강대학교 자연과학부 Teaching Excellence Award, 2016
8. 서강대학교 자연과학부 Award for the Largest Cumulative Impact Factor, 2018
9. 서강대학교 자연과학부 Teaching Excellence Award, 2019
10. 서강대학교 자연과학부 Teaching Excellence Award, 2021

<h4 class="prof-block">Research Interests</h4>

1. Electrical conductivity and structure of polymer nanocomposites
2. Dynamics and structure of fluids in nano-porous materials
3. Dynamics and structure of proteins in cell membranes
4. Monte Carlo (MC) and Molecular Dynamics (MD) simulations of polymers
5. Polymer Reference Interaction Site Model (PRISM) integral equation theory
6. Phase transition and structure of associating copolymers

<h4 class="prof-block">Selected Publications</h4>

{% include smcc_style.liquid %}
<div class="publications">
{% bibliography --group_by none --query @*[selected=true]* %}
</div>
