---
layout: page
permalink: /literatures/
title: literatures
description: This page contains the important papers in my research direction.
nav: true
nav_order: 3
display_categories: [Netlist, Graph]
horizontal: true
---

<!-- pages/literature.md -->
<div class="literatures">
{% if site.enable_literature_categories and page.display_categories %}
  <!-- Display categorized literatures -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_literatures = site.literatures | where: "category", category %}
  {% assign sorted_literatures = categorized_literatures | sort: "importance" %}
  <!-- Generate cards for each literature -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-2">
    {% for literature in sorted_literatures %}
      {% include literatures_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="grid">
    {% for literature in sorted_literatures %}
      {% include literatures.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display literatures without categories -->

{% assign sorted_literatures = site.literatures | sort: "importance" %}

  <!-- Generate cards for each literature -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-2">
    {% for literature in sorted_literatures %}
      {% include literatures_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="grid">
    {% for literature in sorted_literatures %}
      {% include literatures.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
