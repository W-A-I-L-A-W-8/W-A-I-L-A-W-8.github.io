---
layout: default
title: Home
published: true
---

<div id=container>
  Wai Law
  <div id=flip>
    <div><div>Umbraco</div></div>
    <div><div>WordPress</div></div>
    <div><div>Jekyll</div></div>
  </div>
  Developer
</div>

<p><a href="">Read more &rarr;</a></p>

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
