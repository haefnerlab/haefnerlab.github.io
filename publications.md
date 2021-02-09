---
title: Publication
permalink: /publication/
---

For a list of all publications, visit the [google scholar citations profile](https://scholar.google.com/citations?user=Xd_w2fIAAAAJ&hl).

<hr>

<div class="content list">

{% assign sorted = site.data.publications | sort: 'date' | reverse %}
{% for pub in sorted %}

    {% capture year_of_current_post %}
        {{ pub.date | date: "%Y" }}
    {% endcapture %}

    {% capture year_of_previous_post_in_set %}
        {{ sorted[forloop.index].date | date: "%Y" }}
    {% endcapture %}

    {% if forloop.first %}
        <h3>{{ year_of_current_post }}</h3>
        <ul>
    {% endif %}
    <div class="list-item">
        <p class="list-post-title">
                <div class="row">
                    <div class="col-sm-12">
                        
                        <p class="publication-title">
                            {% if pub.link-to-blog != "" and  pub.link-to-blog != nil %}
                                <a href = "/{{pub.link-to-blog}}">
                            {% endif %}
                            
                            {{ pub.title }}
                            
                            {% if pub.link-to-blog != "" and  pub.link-to-blog != nil %}
                                </a>
                            {% endif %}
                        </p>

                        <span class="publication-subtitle">
                            {{pub.authors}}
                        </span>

                        <p class = "publication-journal">
                            {{pub.journal}}, {{pub.date | date: "%B %Y" }}
                        </p>
                        {% comment %}
                        <p class="list-post-title">
                        Keywords: {{pub.keywords}}
                        </p>
                        {% endcomment %}

                        
                        <p class="list-post-title">
                        {% if pub.link-pdf != "" and pub.link-pdf != nil %}
                        <a href="/pdfs/{{pub.link-pdf}}">[ PDF ]</a>
                        {% endif %}
                        {% if pub.link-journal != "" and pub.link-journal != nil %}
                        <a class = "publication-journal" href = "{{pub.link-journal}}">[ Journal Link ]</a>
                        {% endif %}
                        </p>
                        <!-- <p class="list-detail" >
                            {{ pub.content | strip_html }}
                        </p> -->
                        {% if pub.abstract-mini != "" and pub.abstract-mini != nil %}
                        <p class="list-detail" >
                            {{ pub.abstract-mini | strip_html }}
                        </p>
                        {% endif %}
                    </div>
                </div>
        </p>
    </div>

    {% if forloop.last %}
        </ul>
    {% else %}
        {% if year_of_current_post != year_of_previous_post_in_set %}
            <!-- </ul> -->
            <h3>{{ year_of_previous_post_in_set }}</h3>
            <ul>
        {% endif %}
    {% endif %}
{% endfor %}


<h3>Copyright Notice</h3>

<p>The documents listed here are available for downloading and have been provided as a means to ensure timely dissemination of scholarly and technical work on a noncommercial basis. Copyright and all rights therein are maintained by the authors or by other copyright holders, notwithstanding that they have offered their works here electronically. It is understood that all persons copying this information will adhere to the terms and constraints invoked by each author's copyright. These works may not be re-posted without the explicit permission of the copyright holder.</p>
