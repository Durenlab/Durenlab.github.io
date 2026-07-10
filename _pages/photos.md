---
layout: default
title: Photos
permalink: /photos/
---

<h1>Photos</h1>

{% for event in site.data.pics %}

<h2>{{ event.title }}</h2>
<p>{{ event.description }}</p>

<div id="{{ event.id }}Carousel" class="carousel slide event-carousel" data-ride="carousel">
  <ol class="carousel-indicators">
    {% for image in event.images %}
    <li data-target="#{{ event.id }}Carousel" data-slide-to="{{ forloop.index0 }}" {% if forloop.first %}class="active"{% endif %}></li>
    {% endfor %}
  </ol>

  <div class="carousel-inner">
    {% for image in event.images %}
    <div class="item {% if forloop.first %}active{% endif %}">
      <img src="{{ site.baseurl }}/images/Photos_images/{{ event.folder }}/{{ image.file }}" alt="{{ image.caption }}">
      <div class="carousel-caption">{{ image.caption }}</div>
    </div>
    {% endfor %}
  </div>

  <a class="left carousel-control" href="#{{ event.id }}Carousel" role="button" data-slide="prev">
    <span class="glyphicon glyphicon-chevron-left" aria-hidden="true"></span>
  </a>
  <a class="right carousel-control" href="#{{ event.id }}Carousel" role="button" data-slide="next">
    <span class="glyphicon glyphicon-chevron-right" aria-hidden="true"></span>
  </a>
</div>

<hr>

{% endfor %}
