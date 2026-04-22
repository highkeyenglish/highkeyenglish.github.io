---
layout: page
title: tutors
permalink: /tutors/
description: 
nav: true
nav_order: 3
display_categories: [tutors]
horizontal: false
---

<div class="explore-grid">

  <a href="/macbeth" class="card large">
    <img src="/assets/img/macbeth.jpg" alt="Macbeth">
    <div class="card-text">
      <h3>Macbeth</h3>
    </div>
  </a>

  <a href="/poetry" class="card">
    <img src="/assets/img/poetry.jpg">
    <div class="card-text">
      <h3>Poetry</h3>
    </div>
  </a>

  <a href="/a-christmas-carol" class="card tall">
    <img src="/assets/img/acc">
    <div class="card-text">
      <h3>A Christmas Carol</h3>
    </div>
  </a>

</div>

<!-- pages/projects.md -->
<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display projects without categories -->

{% assign sorted_projects = site.projects | sort: "importance" %}

  <!-- Generate cards for each project -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>

<style>
.category {
  display: none;
}
</style>
