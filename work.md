---
layout: page
title: Work
permalink: /work/
published: true
navigation_weight: 3
---

# What's been happening.

- Built this website on Jekyll a few months ago and currently in the process of making UX improvements and adding more useful functionality such as, configuring 'collections' which this page is part of and including categories.
- Migrating a Cuba specialist travel site to Umbraco CMS.
- Learning Python.
- Making changes to Umbraco templates and document types for one of the travel brands I currently work for, traveldirect.co.uk.
- Working as part a team to finalise a practical GIT environment strategy (ENV) to compliment our team workflow.

<hr />

### Some recent projects.
There's more to come but I'm yet to find the time to write my content and upload it.

{% for work in site.work %}
<h3>
<a href="{{ work.url | prepend: site.baseurl }}">{{ work.title }}</a>
</h3>
{% endfor %}

<hr />
