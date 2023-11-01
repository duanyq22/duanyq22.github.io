---
layout: page
permalink: /publications_topic/
title: Publications
topics_MTL: [multi-task learning]
topics_batchRL: [policy evaluation, optimal policy learning]
topics_aggreg: [state aggregation, state embedding]
nav: false
---

<div class="publications">

<h1>Off-line reinforcement learning</h1>

{% for t in page.topics_batchRL %}
  <h2 class="topic">{{t}}</h2>
  {% bibliography -f papers -q @*[topic={{t}}]* %}
{% endfor %}

<h1>Multi-task learning</h1>

{% for t in page.topics_MTL %}
  <h2 class="topic">{{t}}</h2>
  {% bibliography -f papers -q @*[topic={{t}}]* %}
{% endfor %}


<h1>Dimensionality reduction</h1>

{% for t in page.topics_aggreg %}
  <h2 class="topic">{{t}}</h2>
  {% bibliography -f papers -q @*[topic={{t}}]* %}
{% endfor %}

</div>
