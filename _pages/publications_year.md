---
layout: page
permalink: /publications_year/
title: Publications (by year)
years: [2021, 2020, 2019]
nav: false
---

<div class="publications">

{% for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

</div>
