---
layout: default
title: Work
permalink: /work/
published: true
---

<div class="works">
  {% for work in site.works %}
    {% if work.type != "portfolio" %}
    <article class="work">

      <h2><a href="{{ site.baseurl }}{{ work.url }}">{{ work.title }}</a></h2>

      <!--- <div class="entry">
        {{ work.excerpt | truncate: 25 }}
      </div> --->

      <a href="{{ site.baseurl }}{{ work.url }}" class="read-more">Read &rarr;</a>
    </article>
    {% endif %}
  {% endfor %}
</div>
