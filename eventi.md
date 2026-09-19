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

{% assign eventi_futuri = site.data.eventi | sort: "data" %}
{% if eventi_futuri.size > 0 %}
<ul class="eventi-list">
  {% for evento in eventi_futuri %}
  <li>
    <strong>{{ evento.data | date: "%d %B %Y" }}</strong> — {{ evento.titolo }}<br>
    <em>{{ evento.luogo }}</em>
    <p>{{ evento.descrizione }}</p>
    {% if evento.url and evento.url != "" %}<a href="{{ evento.url }}">Maggiori informazioni &rarr;</a>{% endif %}
  </li>
  {% endfor %}
</ul>
{% else %}
<p>Nessun evento in programma al momento: seguici sui nostri canali per essere avvisato dei prossimi appuntamenti.</p>
{% endif %}

Gli eventi vengono annunciati anche sul nostro [canale Telegram](https://t.me/{{ site.social.telegram }})
e in [mailing list](/partecipa/).
