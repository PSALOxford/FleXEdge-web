---
title: "FleXEdge Project - Publications"
layout: gridlay
excerpt: "FleXEdge Project -- Publications."
sitemap: false
permalink: /publications/
---

# Publications

{% assign number_printed = 0 %}
{% for publi in site.data.publist %}

{% if publi.highlight == 1 %}

<div class="well">
<ul class="flex-container">
<li class="flex-item1">
  {% if publi.image %}
    <img src="{{ site.url }}{{ site.baseurl }}/images/pubpic/{{ publi.image }}" class="img-responsive publi-image" />
  {% endif %}
</li>
<li class="flex-item2">
  <strong> {{ publi.title }}</strong> <br />
  <em>{{ publi.authors }} </em><br />
  {{ publi.display }} {% if publi.year %}({{publi.year}}){% endif %}<br/>
  {% if publi.link.url %}<a href="{{ publi.link.url }}" target="_blank"><button class="btn-pdf">PDF</button></a>{% endif %}
  {% if publi.code %}<a href="{{ publi.code }}" target="_blank"><button class="btn-pdf">CODE</button></a>{% endif %}
  <button class="btn-abstract" onclick="toggleAbstract('abstract{{ forloop.index }}')">ABSTRACT</button>
  <div id="abstract{{ forloop.index }}" class="abstract-content" style="display:none;">
    <p>{{ publi.description }}</p>
  </div>
</li>
</ul>

</div>

{% assign number_printed = number_printed | plus: 1 %}

{% endif %}
{% endfor %}

<p> &nbsp; </p>
