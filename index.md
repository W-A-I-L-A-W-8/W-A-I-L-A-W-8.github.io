---
layout: default
title: Home
published: true
---

##### Front End Developer
# Wai Law
[My story &rarr;](/about/)

<hr />

{% include review-mike.html %}

<hr />

<div class="posts">
  {% for post in site.posts limit:2 %}
    {% if post.type != "portfolio" %}
    <article class="post">

      <h2><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h2>

      <div class="entry">
        {{ post.excerpt | truncate: 25 }}
      </div>

      <a href="{{ site.baseurl }}{{ post.url }}" class="read-more">Read &rarr;</a>
    </article>
    {% endif %}
  {% endfor %}
</div>

<hr />
