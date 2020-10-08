---
title: test2
permalink: /test2/
---

{% for post in site.posts %}
<article>
    {% capture year_of_current_post %}
        {{ post.date | date: "%Y" }}
    {% endcapture %}

    {% capture year_of_previous_post_in_set %}
        {{ site.posts[forloop.index].date | date: "%Y" }}
    {% endcapture %}

    {% if forloop.first %}
        <h1>{{ year_of_current_post }}</h1>
        <ul>
    {% endif %}
        
        <li><a href="{{ post.url }}">{{ post.title }}</a></li>

    {% if forloop.last %}
        </ul>
        </article>
    {% else %}
    
        {% if year_of_current_post != year_of_previous_post_in_set %}
            <!-- </ul> -->
            <h1>{{ year_of_previous_post_in_set }}</h1>
            <ul>
        {% endif %}
    {% endif %}

{% endfor %}