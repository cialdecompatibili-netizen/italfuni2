---
layout: single
title: "Servizi"
permalink: /servizi/
author_profile: false
classes: wide
---

{%- comment -%} Elenco principale: solo i servizi base (senza campo citta). Le pagine per citta stanno nella sezione "Dove operiamo" qui sotto, create da sole da site.servizi. {%- endcomment -%}
{% assign base = site.servizi | where_exp: "s", "s.citta == nil" | sort: "ordine" %}
{% include ex-lista.html items=base vista="riga" cta="Scopri il servizio" %}

## Dove operiamo

{% assign citta_list = "Roma,Viterbo,Rieti,Latina,Frosinone" | split: "," %}
{%- for c in citta_list %}
{%- assign pg = site.servizi | where: "citta", c | sort: "title" %}
{%- if pg.size > 0 %}
### {{ c }} e provincia

<ul>
{%- for s in pg %}
<li><a href="{{ s.url | relative_url }}">{{ s.title }}</a></li>
{%- endfor %}
</ul>
{%- endif %}
{%- endfor %}
