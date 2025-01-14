---
layout: page
permalink: /teaching/
title: teaching
description: Teaching is not all you need.
nav: true
nav_order: 2
display_categories: [SJTU, CUHK]
horizontal: true
---

<!-- pages/teaching.md -->
<div class="teaching">
{% if site.enable_teaching_categories and page.display_categories %}
  <!-- Display categorized teachings -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_teachings = site.teachings | where: "category", category %}
  {% assign sorted_teachings = categorized_teachings | sort: "importance" %}
  <!-- Generate cards for each teaching -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-2">
    {% for teaching in sorted_teachings %}
      {% include teachings_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="grid">
    {% for teaching in sorted_teachings %}
      {% include teachings.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display teachings without categories -->

{% assign sorted_teachings = site.teachings | sort: "importance" %}

  <!-- Generate cards for each teaching -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-2">
    {% for teaching in sorted_teachings %}
      {% include teachings_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="grid">
    {% for teaching in sorted_teachings %}
      {% include teachings.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
