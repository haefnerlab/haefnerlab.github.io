---
title: test
permalink: /test/
---

{% for post in site.posts %}
<article>
        <time datetime="{{ post.date | date: "%Y-%m-%d" }}">
                {{ post.date | date_to_string }}
        </time>
        <h1><a href="{{ post.url }}">{{ post.title }}</a></h1>
      
</article>
{% endfor %}