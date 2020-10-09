---
title: Publication
permalink: /publication/
---

All info here: [google scholar citations profile](https://scholar.google.com/citations?user=Xd_w2fIAAAAJ&hl).

<hr>

<div class="content list">
{% for pub in site.data.publications %}
    {% capture year_of_current_post %}
        {{ pub.date | date: "%Y" }}
    {% endcapture %}

    {% capture year_of_previous_post_in_set %}
        {{ site.data[forloop.index].date | date: "%Y" }}
    {% endcapture %}

    {% if forloop.first %}
        <h1>{{ year_of_current_post }}</h1>
        <ul>
    {% endif %}
    <div class="list-item">
        <p class="list-post-title">
                <div class="row">
                    <div class="col-sm-12">
                        <h3 class="post-title">
                            {{ pub.title }}
                        </h3>
                        <p class="list-post-title">
                        posted on {{ pub.date | date: "%B %-d, %Y" }}
                        </p>
                        <p class="list-detail" >
                            {{ pub.content | strip_html | truncatewords:30 }}
                        </p>
                    </div>
                </div>
        </p>
    </div>
    <hr/>

    {% if forloop.last %}
        </ul>
    {% else %}
        {% if year_of_current_post != year_of_previous_post_in_set %}
            <!-- </ul> -->
            <h1>{{ year_of_previous_post_in_set }}</h1>
            <ul>
        {% endif %}
    {% endif %}
{% endfor %}

</div>
