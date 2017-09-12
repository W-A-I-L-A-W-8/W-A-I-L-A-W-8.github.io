---
layout: default
title: Work
permalink: /work/
published: true
---

# Work
Some recent projects.

{% for work in site.work %}
  <h2>
    <a href="{{ work.url | prepend: site.baseurl }}">{{ work.title }}</a>
  </h2>
{% endfor %}
