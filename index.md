---
layout: home
title: Kernel
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

> Technical Writing on AI & Developer Tools
> Practical insights and opinionated perspectives on productivity and development workflows.
