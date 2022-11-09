---
layout: page
permalink: /t-shirts/
title: T-shirt designs
description: My T-shirt designs
nav: false
display_categories: [Princeton University, Peking University]
horizontal: false
---

<div class="t-shirts">
  {% if site.enable_t-shirt_categories and page.display_categories %}
  <!-- Display categorized t-shirts -->
    {% for category in page.display_categories %}
      <h2 class="category">{{category}}</h2>
      {% assign categorized_t-shirts = site.t-shirts | where: "category", category %}
      {% assign sorted_t-shirts = categorized_t-shirts | sort: "importance" %}
      <!-- Generate cards for each t-shirt -->
      {% if page.horizontal %}
        <div class="container">
          <div class="row row-cols-2">
          {% for t-shirt in sorted_t-shirts %}
            {% include t-shirts_horizontal.html %}
          {% endfor %}
          </div>
        </div>
      {% else %}
        <div class="grid">
          {% for t-shirt in sorted_t-shirts %}
            {% include t-shirts.html %}
          {% endfor %}
        </div>
      {% endif %}
    {% endfor %}

  {% else %}
  <!-- Display t-shirts without categories -->
    {% assign sorted_t-shirts = site.t-shirts | sort: "importance" %}
    <!-- Generate cards for each t-shirt -->
    {% if page.horizontal %}
      <div class="container">
        <div class="row row-cols-2">
        {% for t-shirt in sorted_t-shirts %}
          {% include t-shirts_horizontal.html %}
        {% endfor %}
        </div>
      </div>
    {% else %}
      <div class="grid">
        {% for t-shirt in sorted_t-shirts %}
          {% include t-shirts.html %}
        {% endfor %}
      </div>
    {% endif %}

  {% endif %}

</div>
