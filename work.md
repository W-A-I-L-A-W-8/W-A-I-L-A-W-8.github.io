---
layout: page
title: Work
permalink: /work/
published: true
---

## Recent work
More examples of my work can be provided on request.  You will also find two of favourite case studies on my [Behance profile &rarr;](https://www.behance.net/jwchunglaweec1)

<div class="posts">
  {% for work in site.work %}
  <h5>
  <a href="{{ work.url | prepend: site.baseurl }}">{{ work.title }}</a>
  </h5>
  {% endfor %}
</div>

---
