---
layout: default
title: Home
published: true
---

##### I'm Wai, a one-man band who can solve your interface problems. I also happen to be an Umbraco Certified Expert and Shopify Partner.

---

I do the following things pretty well:

- **UI Design**, useful, functional experiences.
- **Umbraco**, if it's Umbraco related, I can usually give it my best shot.
- **Shopify**, my newest service, make an online shop that sells itself.

---

##### [For your eyes only, get my resume here >](/docs/cv-webDesignUIUX_wailaw.pdf/)

---

{% include review-mike.html %}

---

##### What's been happening.

- Emigrated to Melbourne, Australia two months ago.
- Contracting at a well known Digital Transformation Specialist designing UI.
- Built this website on Jekyll a few months ago, forever making UX improvements and adding more useful functionality to it such as; configuring 'collections' which this page is part of and including categories.

---

##### Recent projects.
There's more to come here but I'm struggling to find the time to churn out the content. Keep checking, it'll be here soon!

{% for work in site.work %}
<h5>
<a href="{{ work.url | prepend: site.baseurl }}">{{ work.title }}</a>
</h5>
{% endfor %}
<h5>
<a href="{{ site.baseurl }}/categories/umbraco-text-color-picker-rich-text-editor">Umbraco, enable the text-color picker on the rich text editor and add custom colours</a>
</h5>
<h5>
<a href="{{ site.baseurl }}/categories/umbraco-custom-welcome-dashboard/">Create an Umbraco custom welcome dashboard</a>
</h5>

---

{% include review-jonny.html %}

---
