---
layout: page
title: Eventi
permalink: /eventi/
description: Calendario degli incontri, workshop e installation party del Sulmona LUG.
---

Organizziamo incontri periodici aperti a tutti: chi è alle prime armi con Linux, chi vuole
approfondire un argomento specifico, chi ha semplicemente voglia di conoscere altre persone
appassionate di software libero.

## Prossimi eventi

{% assign oggi = site.time | date: "%Y-%m-%d" %}
{% assign eventi = site.data.eventi | sort: "data" %}
{% assign n_futuri = 0 %}
{% for evento in eventi %}{% assign d = evento.data | date: "%Y-%m-%d" %}{% if d >= oggi %}{% assign n_futuri = n_futuri | plus: 1 %}{% endif %}{% endfor %}
{% if n_futuri > 0 %}
<ul class="eventi-list">
  {% for evento in eventi %}
  {% assign d = evento.data | date: "%Y-%m-%d" %}
  {% if d >= oggi %}
  {% assign mese_idx = evento.data | date: "%m" | plus: 0 | minus: 1 %}
  <li>
    <strong>{{ evento.data | date: "%-d" }} {{ site.data.mesi_it[mese_idx] }} {{ evento.data | date: "%Y" }}{% if evento.orario and evento.orario != "" %}, ore {{ evento.orario }}{% endif %}</strong> — {{ evento.titolo }}<br>
    <em>{{ evento.luogo }}</em>
    <p>{{ evento.descrizione }}</p>
    {% if evento.url and evento.url != "" %}<a href="{{ evento.url }}">Maggiori informazioni &rarr;</a>{% endif %}
  </li>
  {% endif %}
  {% endfor %}
</ul>
{% else %}
<p>Nessun evento in programma al momento: seguici sui nostri canali per essere avvisato dei prossimi appuntamenti.</p>
{% endif %}

Gli eventi vengono annunciati anche sul nostro [canale Telegram](https://t.me/{{ site.social.telegram }})
e in [mailing list](/partecipa/).

{% if n_futuri < eventi.size %}
## Eventi passati

{% assign eventi_passati = eventi | reverse %}
<ul class="eventi-list">
  {% for evento in eventi_passati %}
  {% assign d = evento.data | date: "%Y-%m-%d" %}
  {% if d < oggi %}
  {% assign mese_idx = evento.data | date: "%m" | plus: 0 | minus: 1 %}
  <li>
    <strong>{{ evento.data | date: "%-d" }} {{ site.data.mesi_it[mese_idx] }} {{ evento.data | date: "%Y" }}</strong> — {{ evento.titolo }}
    {% if evento.url and evento.url != "" %}<br><a href="{{ evento.url }}">Rivedi l'evento &rarr;</a>{% endif %}
  </li>
  {% endif %}
  {% endfor %}
</ul>
{% endif %}
