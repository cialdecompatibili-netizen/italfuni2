---
redirect_from:
  - /news/
layout: single
title: Blog
permalink: /blog/
author_profile: false
classes: wide
share: false
---

<style>
.blog-list { list-style: none; padding: 0; margin: 2em 0 0; }

.blog-item {
  position: relative; /* serve al link che copre tutta la card */
  display: flex;
  gap: 2.6rem;
  align-items: flex-start;
  padding: 1.6rem;
  margin: 0 0 1.2rem;
  border: 1px solid #e8e8e8;
  border-radius: 12px;
  background: #fff;
  transition: background 0.25s, box-shadow 0.25s, transform 0.25s, border-color 0.25s;
  -webkit-tap-highlight-color: transparent;
}
/* TUTTA LA CARD CLICCABILE: il link del titolo si estende su tutta la card (un solo link vero, ok per Google e tastiera). Pillole, tag e bottone restano cliccabili sopra (z-index). */
.blog-title::after { content: ''; position: absolute; inset: 0; z-index: 1; border-radius: 12px; }
.blog-cat, .blog-tag, .blog-readmore { position: relative; z-index: 2; }
/* hover solo dove c'e' un mouse; sul touch resta un effetto al tocco (:active) cosi' non rimane 'appiccicato' */
@media (hover: hover) {
  .blog-item:hover { background: #f7faf0; border-color: #95d600; box-shadow: 0 8px 24px rgba(21,25,29,.10); transform: translateY(-2px); }
  .blog-item:hover .blog-title { color: #3f6b00; text-decoration: underline !important; text-underline-offset: 3px; }
  .blog-item:hover .blog-readmore { background: #95d600; color: #15191d; }
}
.blog-item:active { background: #f1f6e4; transform: scale(.995); }
.blog-item:focus-within { outline: 2px solid #95d600; outline-offset: 2px; }

.blog-img {
  flex-shrink: 0;
  width: 220px;
  height: 155px;
  overflow: hidden;
  background: #f5f5f5;
}
.blog-img img { width: 100%; height: 100%; object-fit: cover; display: block; transition: transform 0.55s ease; }
.blog-item:hover .blog-img img { transform: scale(1.05); }
.blog-img-empty {
  width: 100%; height: 100%; background: #f0f0f0;
  display: flex; align-items: center; justify-content: center;
  font-size: 22px; color: #ccc;
}

.blog-body { flex: 1; min-width: 0; display: flex; flex-direction: column; gap: 0.6rem; }

/* PILL CATEGORIA */
.blog-cats { display: flex; gap: 8px; flex-wrap: wrap; }
.blog-cat {
  font-size: 0.68rem;
  font-weight: 700;
  letter-spacing: 0.14em;
  text-transform: uppercase;
  color: #3f6b00;
  background: transparent;
  border: 1.5px solid #3f6b00;
  border-radius: 999px;
  padding: 3px 12px;
  text-decoration: none !important;
  box-shadow: 0 2px 6px rgba(149,214,0, 0.15);
  transition: background 0.18s, color 0.18s, box-shadow 0.18s, transform 0.18s;
  display: inline-block;
}
.blog-cat:hover {
  background: #95d600;
  color: #15191d !important;
  text-decoration: none !important;
  transform: translateY(-1px);
  box-shadow: 0 4px 12px rgba(149,214,0, 0.40);
}

/* TITOLO — no sottolineatura di default, appare solo all'hover */
.blog-title {
  font-size: clamp(1.05rem, 2vw, 1.35rem);
  font-weight: 500; line-height: 1.4; color: #111;
  text-decoration: none !important; display: block;
}

.blog-excerpt {
  font-size: clamp(0.9rem, 1.5vw, 1.05rem);
  font-weight: 300; color: #888; line-height: 1.9;
  display: -webkit-box; -webkit-line-clamp: 3;
  -webkit-box-orient: vertical; overflow: hidden;
}

.blog-meta { font-size: 0.78rem; color: #bbb; display: flex; align-items: center; gap: 0.5rem; }
.blog-meta-sep { color: #ddd; }

.blog-footer {
  display: flex; align-items: center; justify-content: space-between;
  flex-wrap: wrap; gap: 0.5rem;
  margin-top: 0.4rem;
}

.blog-tags { display: flex; gap: 8px; flex-wrap: wrap; }
.blog-tag {
  font-size: 0.7rem; letter-spacing: 0.07em; color: #ccc;
  text-decoration: none !important;
}
.blog-tag:hover { color: #111; text-decoration: none !important; }

/* BOTTONE LEGGI TUTTO */
.blog-readmore {
  font-size: 0.72rem;
  font-weight: 600;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: #555;
  text-decoration: none !important;
  background: #f2f2f2;
  border-radius: 999px;
  padding: 6px 16px;
  white-space: nowrap;
  border: none;
  transition: background 0.2s, color 0.2s;
}
.blog-readmore:hover {
  background: #e4e4e4;
  color: #111;
  text-decoration: none !important;
}

@media (max-width: 640px) {
  .blog-item { flex-direction: column; gap: 1.2rem; padding: 1.1rem; }
  .blog-img { width: 100%; height: 200px; }
  .blog-footer { flex-direction: column; align-items: flex-start; }
}
</style>

<ul class="blog-list">
  {% for post in site.posts %}
  <li class="blog-item">
    <div class="blog-img">
      {% if post.header.teaser %}
        <img src="{{ post.header.teaser | relative_url }}" alt="{{ post.title }}">
      {% else %}
        <div class="blog-img-empty">✦</div>
      {% endif %}
    </div>
    <div class="blog-body">
      {% if post.categories.size > 0 %}
      <div class="blog-cats">
        {% for cat in post.categories limit:2 %}
        <a href="{{ '/categories/#' | prepend: site.baseurl }}{{ cat | slugify }}" class="blog-cat">{{ cat }}</a>
        {% endfor %}
      </div>
      {% endif %}
      <a href="{{ post.url | relative_url }}" class="blog-title">{{ post.title }}</a>
      <div class="blog-excerpt">{{ post.excerpt | strip_html | truncate: 200 }}</div>
      <div class="blog-meta">
        <time>{{ post.date | date: "%d %b %Y" }}</time>
        {% if post.author %}<span class="blog-meta-sep">·</span><span>{{ post.author }}</span>{% endif %}
      </div>
      <div class="blog-footer">
        {% if post.tags.size > 0 %}
        <div class="blog-tags">
          {% for tag in post.tags limit:3 %}
          <a href="{{ '/tags/#' | prepend: site.baseurl }}{{ tag | slugify }}" class="blog-tag"># {{ tag }}</a>
          {% endfor %}
        </div>
        {% endif %}
        <a href="{{ post.url | relative_url }}" class="blog-readmore">Leggi tutto →</a>
      </div>
    </div>
  </li>
  {% endfor %}
</ul>
