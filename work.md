---
layout: page
title: Work
permalink: /work/
published: true
navigation_weight: 4
---

# What's been happening.

- Emigrated to Melbourne, Australia recently. Considering my next move.
- Built this website on Jekyll a few months ago and and still making UX improvements and adding more useful functionality to it such as; configuring 'collections' which this page is part of and including categories.
- Learning Python.
- Attempting to finalise a practical GIT environment strategy (ENV) to compliment our team workflow.

<hr />

### Some recent projects.
There's more to come here but I'm struggling to find the time to churn out the content. Keep checking, it'll be here soon!

{% for work in site.work %}
<h3>
<a href="{{ work.url | prepend: site.baseurl }}">{{ work.title }}</a>
</h3>
{% endfor %}

<hr />
