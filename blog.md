---
layout: default
title: Notes
permalink: /notes/
published: true
---

<div class="posts">
  {% for post in site.posts %}
    {% if post.type != "portfolio" %}
    <!-- <article class="post"> -->

      <h5><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h5>

      <!--- <div class="entry">
        {{ post.excerpt | truncate: 25 }}
      </div> --->

      <a href="{{ site.baseurl }}{{ post.url }}" class="read-more">Read &rarr;</a>
    <!-- </article> -->
    {% endif %}
  {% endfor %}
</div>
