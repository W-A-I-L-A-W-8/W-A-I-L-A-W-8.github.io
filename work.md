---
layout: page
title: Work
permalink: /work/
published: true
---

## Recent work
There's more I can show you on request, just ask me.

<div class="posts">
  {% for work in site.work %}
  <h5>
  <a href="{{ work.url | prepend: site.baseurl }}">{{ work.title }}</a>
  </h5>
  {% endfor %}
</div>

---
