---
redirect_from:
  - /servizio/servizi-per-provincia/
layout: single
title: "Servizi"
permalink: /servizi/
author_profile: false
classes: wide
---

{%- comment -%} Elenco principale: solo i servizi base (senza campo citta). Le pagine per citta stanno nella sezione "Dove operiamo" qui sotto, create da sole da site.servizi. {%- endcomment -%}
{% assign base = site.servizi | where_exp: "s", "s.citta == nil" | sort: "ordine" %}
{% include ex-lista.html items=base vista="riga" cta="Scopri il servizio" %}

## Servizi per provincia

<style>
.prv{display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:1rem;margin:1.2rem 0 2rem}
.prv a{position:relative;display:flex;flex-direction:column;gap:.25rem;padding:1.3rem 1.4rem;border:1px solid #dfe3d6;border-radius:14px;background:#fff;color:var(--ex-ink,#15191d);text-decoration:none;overflow:hidden;transition:transform .25s ease,box-shadow .25s ease,border-color .25s ease,background .25s ease}
.prv a::before{content:"";position:absolute;inset:0;background:var(--ex-y,#efbb20);opacity:0;transition:opacity .25s ease;z-index:0}
.prv a>*{position:relative;z-index:1}
.prv b{font-size:1.15rem;font-weight:700;letter-spacing:-.01em}
.prv small{color:#5a5a52;font-size:.85rem;transition:color .25s ease}
.prv i{font-style:normal;margin-top:.7rem;font-size:1.3rem;line-height:1;transition:transform .25s ease}
.prv a:hover,.prv a:focus-visible{transform:translateY(-4px);box-shadow:0 12px 28px rgba(21,25,29,.12);border-color:var(--ex-y,#efbb20)}
.prv a:hover::before,.prv a:focus-visible::before{opacity:.18}
.prv a:hover i,.prv a:focus-visible i{transform:translateX(6px)}
.prv a:hover small{color:var(--ex-ink,#15191d)}
@media (prefers-reduced-motion:reduce){.prv a,.prv a::before,.prv i{transition:none}.prv a:hover{transform:none}}
</style>
<div class="prv">
<a href="{{ '/servizi/provincia/roma/' | relative_url }}"><b>Roma</b><small>e provincia</small><i>&rarr;</i></a>
<a href="{{ '/servizi/provincia/viterbo/' | relative_url }}"><b>Viterbo</b><small>e provincia</small><i>&rarr;</i></a>
<a href="{{ '/servizi/provincia/rieti/' | relative_url }}"><b>Rieti</b><small>e provincia</small><i>&rarr;</i></a>
<a href="{{ '/servizi/provincia/latina/' | relative_url }}"><b>Latina</b><small>e provincia</small><i>&rarr;</i></a>
<a href="{{ '/servizi/provincia/frosinone/' | relative_url }}"><b>Frosinone</b><small>e provincia</small><i>&rarr;</i></a>
</div>