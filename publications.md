---
layout: default
title: Publications
permalink: /publications/
---

<div class="page-content">

{% assign sorted = site.data.publications | sort: "year" | reverse %}
{% assign current_year = "" %}

{% for pub in sorted %}
  {% if pub.year != current_year %}
    {% assign current_year = pub.year %}
    <p class="pub-year">{{ pub.year }}</p>
  {% endif %}
  <div class="pub-item">
    <span class="pub-title">{{ pub.title }}</span><br>
    <span class="pub-authors">{{ pub.authors }}</span><br>
    <span class="pub-venue">{{ pub.venue }}</span>
    <div class="pub-links">
      {% for link in pub.links %}
      <a href="{{ link.url }}"{% unless link.url == "#" %}target="_blank"{% endunless %}>{{ link.label }}</a>
      {% endfor %}
    </div>
  </div>
{% endfor %}

</div>
