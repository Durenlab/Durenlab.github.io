---
title: "Duren Lab - Publications"
layout: gridlay
excerpt: "Duren Lab -- Publications."
sitemap: false
permalink: /publications/
---

<style>
  /* 1. Ensure the row handles equal height children */
  .row {
    display: flex;
    flex-wrap: wrap;
  }
  
  /* 2. Force the 'well' boxes to fill the full height of the column */
  .well {
    display: flex;
    flex-direction: column;
    height: 100%;
    margin-bottom: 20px;
    padding: 20px;
  }

  /* 3. The Image Container: Fixed height and centered */
  .pub-img-container {
    width: 100%;
    height: 180px; /* Reduced slightly for better fit */
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #fff;
    margin: 15px 0;
    border: 1px solid #eee;
    border-radius: 4px;
  }

  .pub-img-container img {
    max-height: 90%; /* Leaves a small margin inside the box */
    max-width: 95%;
    object-fit: contain;
  }

  /* 4. Push the authors and links to the bottom so they align across boxes */
  .well p:last-of-type {
    margin-top: auto;
  }
</style>

# Publications

## Highlights

(For a full list see [below](#full-list) or go to [Google Scholar](https://scholar.google.com/citations?user=STB0IoUAAAAJ))

{% assign number_printed = 0 %}
{% for publi in site.data.publist %}
  {% if publi.highlight == 1 %}
    {% assign even_odd = number_printed | modulo: 2 %}
    {% if even_odd == 0 %}
<div class="row">
    {% endif %}
    
    <div class="col-sm-6">
      <div class="well">
        <pubtit>{{ publi.title }}</pubtit>
        
        <div class="pub-img-container">
          <img src="{{ site.url }}{{ site.baseurl }}/images/pubpic/{{ publi.image }}" alt="{{ publi.title }}">
        </div>

        <p>{{ publi.description }}</p>
        <p><em>{{ publi.authors }}</em></p>
        <p><strong><a href="{{ publi.link.url }}">{{ publi.link.display }}</a></strong></p>
        
        {% if publi.news1 %}
        <p class="text-danger"><strong>{{ publi.news1 }}</strong></p>
        {% endif %}
        
        {% if publi.news2 %}
        <p>{{ publi.news2 }}</p>
        {% endif %}
      </div>
    </div>

    {% assign number_printed = number_printed | plus: 1 %}
    {% assign even_odd_end = number_printed | modulo: 2 %}
    {% if even_odd_end == 0 %}
</div>
    {% endif %}
  {% endif %}
{% endfor %}

{% assign final_check = number_printed | modulo: 2 %}
{% if final_check != 0 %}
</div>
{% endif %}

<p> &nbsp; </p>

## Full List

{% for publi in site.data.publist %}
<p>
  {{ publi.title }} <br />
  <em>{{ publi.authors }} </em><br />
  <a href="{{ publi.link.url }}">{{ publi.link.display }}</a>
</p>
{% endfor %}
