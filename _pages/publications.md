---
layout: page
permalink: /publications/
title: Publications
description: 
nav: true
nav_order: 1
sortby: true        # true: Sort by types | false: Sort by years
years: [2025, 2024, 2023, 2022, 2021, 2020, 2019]
sections:
  - bibquery: "@preprint"
    text: "Preprint articles"
  - bibquery: "@article"
    text: "Journal articles"
  - bibquery: "@inproceedings"
    text: "Conference Proceedings (Work in Progress!)"
  - bibquery: "@misc|@thesis"
    text: "Thesis"
---

<!-- - bibquery: "@book|@incollection" -->
<!-- text: "Books and Book chapters" -->
<!-- _pages/publications.md -->


<div class="publications">
  <a href="https://scholar.google.com/citations?user=GPYQNbEAAAAJ" style="font-size: 1.5rem;"><b>Google Scholar Profile</b></a>
  <p></p>

  {% include bib_search.liquid %}

  <div style="height: 2rem;"></div>

  {%- for section in page.sections -%}
    <a id="{{ section.text }}" class="center-text" style="font-size: 1.0rem;"></a>
    <p class="center-text" style="font-size: 1.5rem;">{{ section.text }}</p>
    <p style="font-size: 1.0rem;"></p>

    {%- comment -%}
      연도별 루프 제거: 섹션별로 한 번만 bibliography 호출
      최신이 위로 오도록 정렬 → <ol> 기본 넘버링이 1부터 시작
    {%- endcomment -%}
    <div class="pub-list">
      {%- bibliography -f {{ site.scholar.bibliography }} -q {{ section.bibquery }} --sort_by=year,desc -%}
    </div>
  {%- endfor -%}
</div>