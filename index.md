---
layout: default
title: Home
published: true
---

##### Front End Developer
# Wai Law
[My story &rarr;](/about/)

<hr />

<!-- Recent Posts -->
<div class="related">
    <h2>Recent Posts</h2>
    <ul>
      {% for post in site.related_posts limit:3 %}
        {% if post.type != "portfolio" %}
        <a href="{{ post.url }}">
            <li>
            <h4>{{ post.title }}</h4>
            </li>
        </a>
        {% endif %}
      {% endfor %}
    </ul>
</div>
<!-- #Related Posts -->

{% include review-mike.html %}
