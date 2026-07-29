---
layout: default
title: Photos
permalink: /photos/
---

<!-- Include jQuery & Bootstrap JS ONLY (for arrow clicks / sliding mechanism) -->
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.7.1/jquery.min.js"></script>
<script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/js/bootstrap.min.js"></script>

<style>
/* Essential Bootstrap Carousel Layout Styles (Scoped so they won't mess up your page fonts) */
.carousel { position: relative; }
.carousel-inner { position: relative; width: 100%; overflow: hidden; }
.carousel-inner > .item { position: relative; display: none; -webkit-transition: .6s ease-in-out left; transition: .6s ease-in-out left; }
.carousel-inner > .item > img { display: block; max-width: 100%; height: auto; }
.carousel-inner > .active, .carousel-inner > .next, .carousel-inner > .prev { display: block; }
.carousel-inner > .active { left: 0; }
.carousel-inner > .next, .carousel-inner > .prev { position: absolute; top: 0; width: 100%; }
.carousel-inner > .next { left: 100%; }
.carousel-inner > .prev { left: -100%; }
.carousel-inner > .next.left, .carousel-inner > .prev.right { left: 0; }
.carousel-inner > .active.left { left: -100%; }
.carousel-inner > .active.right { left: 100%; }

/* Carousel Controls (Arrows) */
.carousel-control { position: absolute; top: 0; bottom: 0; left: 0; width: 15%; font-size: 20px; color: #fff; text-align: center; opacity: 0.5; filter: alpha(opacity=50); }
.carousel-control.right { right: 0; left: auto; }
.carousel-control:hover, .carousel-control:focus { color: #fff; text-decoration: none; opacity: .9; }
.carousel-control .glyphicon-chevron-left, .carousel-control .glyphicon-chevron-right { position: absolute; top: 50%; z-index: 5; display: inline-block; margin-top: -10px; }
.carousel-control .glyphicon-chevron-left { left: 50%; margin-left: -10px; }
.carousel-control .glyphicon-chevron-right { right: 50%; margin-right: -10px; }

/* Custom Frame & Image Styling */
.event-carousel {
  max-width: 800px;
  margin: 20px auto;
  box-shadow: 0 4px 10px rgba(0,0,0,0.15);
  background-color: #ffffff;
}
.carousel-inner .item {
  height: 450px;
  background-color: #ffffff; /* WHITE BACKGROUND */
}
.carousel-inner .item img {
  width: 100%;
  height: 100%;
  object-fit: contain;
}
.carousel-caption {
  position: absolute;
  right: 15%;
  bottom: 20px;
  left: 15%;
  z-index: 10;
  padding-top: 20px;
  padding-bottom: 20px;
  color: #333333;
  background-color: rgba(255, 255, 255, 0.85);
  text-align: center;
  text-shadow: 0 1px 2px rgba(0,0,0,.6);
}
</style>

# Photos

{% for event in site.data.pics %}

## {{ event.title }}
{{ event.description }}

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
<div class="carousel-caption">
<p>{{ image.caption }}</p>
</div>
</div>
{% endfor %}
</div>

<a class="left carousel-control" href="#{{ event.id }}Carousel" role="button" data-slide="prev">
<span class="glyphicon glyphicon-chevron-left" aria-hidden="true">&#10094;</span>
</a>
<a class="right carousel-control" href="#{{ event.id }}Carousel" role="button" data-slide="next">
<span class="glyphicon glyphicon-chevron-right" aria-hidden="true">&#10095;</span>
</a>
</div>

---

{% endfor %}
