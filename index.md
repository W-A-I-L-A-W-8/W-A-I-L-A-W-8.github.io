---
layout: default
title: Home
published: true
---

{% include welcome-text.html %}

<hr />

{% include review-mike.html %}

<hr />

### Latest Posts:

{% for post in site.posts limit:2 %}
{% if post.type != "portfolio" %}

<h5><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h5>
{{ post.excerpt | truncate: 150 }}
<a href="{{ site.baseurl }}{{ post.url }}" class="read-more">Have a gander &rarr;</a>

{% endif %}
{% endfor %}

<hr />
