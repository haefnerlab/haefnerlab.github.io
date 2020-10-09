---
title: Publication
permalink: /publication3/
---

All info here: [google scholar citations profile](https://scholar.google.com/citations?user=Xd_w2fIAAAAJ&hl).

I will explain later on how to add a new publication. 

<hr>

<div class="content list">
{% for post in site.posts %}
    {% if post.categories contains 'publication' %}
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
        <div class="list-item">
            <p class="list-post-title">
                {% if post.link-active == True %}
                    <a href="{{ post.url | prepend: site.baseurl }}">
                {% endif %}
                    <div class="row">
                        <div class="col-sm-4">
                            <img src="/{% if post.header-img %}{{ post.header-img }}{% else %}{{ site.header-img }}{% endif %}">
                        </div>
                        <div class="col-sm-8">
                            <h3 class="post-title">
                                {{ post.title }}
                            </h3>
                            <p class="list-post-title">
                            posted on {{ post.date | date: "%B %-d, %Y" }}
                            </p>
                            <p class="list-detail" >
                                {{ post.content | strip_html | truncatewords:30 }}
                            </p>
                        </div>
                    </div>
                <hr/>
                {% if post.link-active == True %}
                    </a>
                {% endif %}

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
{% endif %}
{% endfor %}

</div>

<h3>Copyright Notice</h3>

<p>The documents listed here are available for downloading and have been provided as a means to ensure timely dissemination of scholarly and technical work on a noncommercial basis. Copyright and all rights therein are maintained by the authors or by other copyright holders, notwithstanding that they have offered their works here electronically. It is understood that all persons copying this information will adhere to the terms and constraints invoked by each author's copyright. These works may not be re-posted without the explicit permission of the copyright holder.</p>
