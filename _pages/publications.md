---
title: "Duren Lab - Publications"
layout: gridlay
excerpt: "Duren Lab -- Publications."
sitemap: false
permalink: /publications/
---

<style>
  /* This ensures all image boxes are the same height and width */
  .pub-img-container {
    width: 100%;
    height: 200px; /* Fixed height for the image area */
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #fff;
    margin-bottom: 15px;
    overflow: hidden;
    border: 1px solid #f5f5f5;
  }

  .pub-img-container img {
    max-height: 100%;
    max-width: 100%;
    object-fit: contain; /* Keeps original proportions without stretching */
  }

  /* Ensures the "well" boxes stay the same height in each row */
  .well {
    min-height: 520px; /* Adjust this if your descriptions are very long */
    display: flex;
    flex-direction: column;
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

    <div class="col-sm-6 clearfix">
      <div class="well">
        <pubtit>{{ publi.title }}</pubtit>
        
        <div class="pub-img-container">
          <img src="{{ site.url }}{{ site.baseurl }}/images/pubpic/{{ publi.image }}" alt="{{ publi.title }}">
        </div>

        <p>{{ publi.description }}</p>
        <p><em>{{ publi.authors }}</em></p>
        <p><strong><a href="{{ publi.link.url }}">{{ publi.link.display }}</a></strong></p>
        <p class="text-danger"><strong>{{ publi.news1 }}</strong></p>
        <p>{{ publi.news2 }}</p>
      </div>
    </div>

    {% assign number_printed = number_printed | plus: 1 %}
    {% assign even_odd_check = number_printed | modulo: 2 %}
    {% if even_odd_check == 0 %}
    </div>
    {% endif %}
  {% endif %}
{% endfor %}

{% comment %} Close row if the total count of highlights was odd {% endcomment %}
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
