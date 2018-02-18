---
layout: page
title: Work
permalink: /work/
published: true
navigation_weight: 4
---

# What's been happening.

- Emigrated to Melbourne, Australia recently with Permanent Residency. Considering my next move and looking for exciting opportunities in the tech arena.
- Built this website on Jekyll a few months ago, making UX improvements and adding more useful functionality to it such as; configuring 'collections' which this page is part of and including categories.
- Teaching myself React.  I recommend the React documentation and tutorials as a great starting point.
- Finalise a practical GIT environment strategy (ENV) to compliment our team workflow.

<hr />

### Some recent projects.
There's more to come here but I'm struggling to find the time to churn out the content. Keep checking, it'll be here soon!

{% for work in site.work %}
<h3>
<a href="{{ work.url | prepend: site.baseurl }}">{{ work.title }}</a>
</h3>
{% endfor %}

<hr />
