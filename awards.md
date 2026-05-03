---
layout: default
title: Awards & Funding
permalink: /awards/
---

<div class="page-content">

<div class="awards-section">
  <div class="section-label">Fellowships & Awards</div>
  {% for item in site.data.awards.fellowships %}
  <div class="award-item">
    <div class="award-year">{{ item.year }}</div>
    <div class="award-body">
      <div class="award-title">
        {% if item.url %}<a href="{{ item.url }}" target="_blank">{{ item.title }}</a>{% else %}{{ item.title }}{% endif %}
      </div>
      <div class="award-org">{{ item.org }}</div>
      {% if item.detail != "" %}<div class="award-detail">{{ item.detail }}</div>{% endif %}
    </div>
  </div>
  {% endfor %}
</div>

<div class="awards-section">
  <div class="section-label">Research Funding</div>
  {% for item in site.data.awards.funding %}
  <div class="award-item">
    <div class="award-year">{{ item.year }}</div>
    <div class="award-body">
      <div class="award-title">
        {% if item.url %}<a href="{{ item.url }}" target="_blank">{{ item.title }}</a>{% else %}{{ item.title }}{% endif %}
      </div>
      {% if item.detail != "" %}<div class="award-detail">{{ item.detail }}</div>{% endif %}
    </div>
  </div>
  {% endfor %}
</div>

</div>
