---
layout: default
title: Photos
permalink: /photos/
---

<!-- 引入 Bootstrap 3 轮播图所需的 CSS & JS（如果你的全局 layout 已引入可删掉这几行） -->
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/css/bootstrap.min.css">
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.7.1/jquery.min.js"></script>
<script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/js/bootstrap.min.js"></script>

<style>
/* 修复图片自适应与轮播高宽问题 */
.event-carousel {
  max-width: 800px;
  margin: 20px auto;
  box-shadow: 0 4px 10px rgba(0,0,0,0.15);
}
.carousel-inner .item {
  height: 450px; /* 统一轮播高度，防止高低不一 */
  background-color: #000;
}
.carousel-inner .item img {
  width: 100%;
  height: 100%;
  object-fit: contain; /* 完整展示图片，不拉伸不截断 */
}
</style>

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
<div class="carousel-caption">
<h3>{{ image.caption }}</h3>
</div>
</div>
{% endfor %}
</div>

<a class="left carousel-control" href="#{{ event.id }}Carousel" role="button" data-slide="prev">
<span class="glyphicon glyphicon-chevron-left" aria-hidden="true"></span>
<span class="sr-only">Previous</span>
</a>
<a class="right carousel-control" href="#{{ event.id }}Carousel" role="button" data-slide="next">
<span class="glyphicon glyphicon-chevron-right" aria-hidden="true"></span>
<span class="sr-only">Next</span>
</a>
</div>

<hr>

{% endfor %}
