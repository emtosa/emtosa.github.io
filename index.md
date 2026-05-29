---
layout: home
title: CLI-First Developer Blog
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

> This blog is about practical AI productivity for developers who live in the terminal.
> New posts publish directly from the command line — no CMS required.
