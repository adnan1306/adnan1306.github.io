---
layout: default
title: Publications
permalink: /publications/
---

<div class="page-content">

<p class="scholar-note">Check <a href="{{ site.author.scholar }}" target="_blank">Google Scholar <svg viewBox="0 0 16 16" fill="currentColor"><path d="M7.5 1L0 5.5l2.5 1.5V11c0 1.38 2.24 2.5 5 2.5s5-1.12 5-2.5V7l1.5-.9V11.5H15V5.5L7.5 1zM7.5 12C5.57 12 4 11.33 4 10.5S5.57 9 7.5 9 11 9.67 11 10.5 9.43 12 7.5 12z"/></svg></a> for an up to date list.</p>

{% assign sorted = site.data.publications | sort: "year" | reverse %}
{% assign current_year = "" %}

{% for pub in sorted %}
  {% if pub.year != current_year %}
    {% assign current_year = pub.year %}
    <p class="pub-year">{{ pub.year }}</p>
  {% endif %}
  <div class="pub-item">
    <span class="pub-title">{{ pub.title }}</span><br>
    <span class="pub-authors">{{ pub.authors | replace: "M. Adnan", "<span class='my-name'>M. Adnan</span>" }}</span><br>
    <span class="pub-venue">{{ pub.venue }}</span>
    <div class="pub-links">
      {% for link in pub.links %}
      {% if link.url == "#" %}<a href="#">{{ link.label }}</a>{% else %}<a href="{{ link.url }}" target="_blank">{{ link.label }}</a>{% endif %}
      {% endfor %}
    </div>
  </div>
{% endfor %}

</div>
