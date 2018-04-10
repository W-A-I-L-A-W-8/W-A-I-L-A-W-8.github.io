---
layout: default
title: Home
published: true
---

##### I'm Wai, I'm a small business (one-man band) thriving on solving interface problems. I am also an Umbraco Certified Expert and Shopify Partner.

---

I do the following things pretty well:

- **UI Design**, useful, functional experiences.
- **Umbraco**, if it's Umbraco related, I can usually give it my best shot.
- **Shopify**, my newest service, make an online shop that sells itself.

---

##### [Hiring managers, you can get my resume here &rarr;](/docs/cv-webDesignUIUX_wailaw.pdf/)

---

{% include review-mike.html %}

---

##### What I have been up to

- Emigrated to Melbourne, Australia two months ago.
- Contracting at a well known Digital Transformation Specialist designing UI.
- Built this website on Jekyll a few months ago, forever making UX improvements and adding more useful functionality to it such as; configuring 'collections' which this page is part of and including categories.

---

##### Recent work
There's more I can show you on request, just ask me.

{% for work in site.work %}

    <h5><a href="{{ work.url | prepend: site.baseurl }}">{{ work.title }}</a></h5>
    
{% endfor %}


##### Recent scribbles

{% for post in site.posts limit:2 %}
  {% if post.type != "portfolio" %}

    <h5><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h5>

  {% endif %}
{% endfor %}

##### [Read more posts &rarr;](/notes/)

---

{% include review-jonny.html %}

---
