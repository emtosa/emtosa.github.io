---
layout: home
title: emtosa — Personal Blog
---

## Latest Posts

{% for post in site.posts limit:10 %}
### [{{ post.title }}]({{ post.url | relative_url }})
<span class="post-meta">{{ post.date | date: "%B %-d, %Y" }}</span>

{{ post.description }}

{% if post.tags.size > 0 %}
**Tags:** {% for tag in post.tags %}`{{ tag }}`{% unless forloop.last %} {% endunless %}{% endfor %}
{% endif %}

---
{% endfor %}

> Personal writing on technology, AI, developer workflows, and broader community topics.
> Practical when possible, opinionated when useful.
