---
layout: page
title: Archivio Linux Day
permalink: /archivio/
description: >-
  23 anni di storia del Linux Day: l'archivio fotografico del gruppo, dalla prima edizione
  del 2003 a oggi.
---

Era il 2003 quando si tenne la prima edizione del Linux Day a cui il gruppo ha preso parte:
da allora sono passati **23 anni** di incontri, installation party e chiacchierate sul software
libero. Questa pagina raccoglie via via le foto e i ricordi di questi anni, mano a mano che li
ritroviamo.

## La galleria

{% assign edizioni = site.data.archivio_ld | sort: "anno" %}
{% if edizioni.size > 0 %}
<p class="archive-hint">Clicca su una foto per vederla intera.</p>
<div class="archive-gallery">
  {% for edizione in edizioni %}
  {% assign immagini = edizione.immagini %}
  {% assign copertina = immagini.first %}
  {% assign copertina_url = '/assets/images/archivio_LD/' | append: copertina.file | relative_url %}
  <div class="archive-item">
    <a class="archive-cover" href="{{ copertina_url }}" target="_blank" rel="noopener">
      <img src="{{ copertina_url }}" alt="{{ copertina.didascalia | default: edizione.didascalia | default: edizione.anno }}" loading="lazy">
    </a>
    <p class="archive-caption">
      <strong>{{ edizione.anno }}</strong>{% if edizione.didascalia %} — {{ edizione.didascalia }}{% endif %}
    </p>
    {% if immagini.size > 1 %}
    <div class="archive-thumbs">
      {% for foto in immagini offset: 1 %}
      {% assign foto_url = '/assets/images/archivio_LD/' | append: foto.file | relative_url %}
      <a class="archive-thumb" href="{{ foto_url }}" target="_blank" rel="noopener">
        <img src="{{ foto_url }}" alt="{{ foto.didascalia | default: edizione.didascalia | default: edizione.anno }}" loading="lazy">
      </a>
      {% endfor %}
    </div>
    {% endif %}
  </div>
  {% endfor %}
</div>
{% else %}
<p>L'archivio è in costruzione: le prime foto arriveranno presto.</p>
{% endif %}

## Aiutaci a completare l'archivio

Hai foto, locandine o ricordi delle passate edizioni del Linux Day a Sulmona? Scrivici tramite
la pagina [Contatti](/contatti/): ogni contributo aiuta a ricostruire la storia del gruppo.
