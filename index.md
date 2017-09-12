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
<div class="blog-index">  
  {% assign post = site.posts.first %}
  {% assign content = post.content %}
  {% include post_detail.html %}
</div>
<!-- #Related Posts -->

{% include review-mike.html %}
