---
title: People
permalink: /people/
---

<img class='img-responsive center-block' src="/images/people/lab_2019.jpg" width="100%" height="100%" />

{% assign people_sorted = site.people | sort: 'joined' %}

{% assign role_array = "pi|postdoc|gradstudent|researchstaff|undergraduate|visiting|others|alumni" | split: "|" %}

{% for role in role_array %}

{% assign people_in_role = people_sorted | where: 'position', role %}

<!-- Skip section if there's nobody -->
{% if people_in_role.size == 0 %}
  {% continue %}
{% endif %}

<div class="pos_header">
{% if role == 'postdoc' %}
<h3>Postdoctoral Fellows</h3>
 {% elsif role == 'pi' %}
<h3>Principal Investigator</h3>
 {% elsif role == 'gradstudent' %}
<h3>Graduate Students</h3>
 {% elsif role == 'researchstaff' %}
<h3>Research Staff</h3>
 {% elsif role == 'undergraduate' %}
<h3>Undergraduates</h3>
 {% elsif role == 'visiting' %}
<h3>Visiting Scholars</h3>
 {% elsif role == 'others' %}
<h3>Honorary Members</h3>
 {% elsif role == 'alumni' %}
<h3>Alumni</h3>
{% endif %}
</div>

{% if role != 'alumni' %}
<div class="content list people">
  {% for profile in people_sorted %}
    {% if profile.position contains role %}
      <div class="list-item-people">
        <p class="list-post-title">
          {% if profile.avatar %}
            <a href="{{ site.baseurl }}{{ profile.url }}"><img class="profile-thumbnail" src="{{site.baseurl}}/images/people/{{profile.avatar}}"></a>
          {% else %}
            <a href="{{ site.baseurl }}{{ profile.url }}"><img class="profile-thumbnail" src="http://evansheline.com/wp-content/uploads/2011/02/facebook-Storm-Trooper.jpg"></a>
          {% endif %}
          <a class="name" href="{{ site.baseurl }}{{ profile.url }}">{{ profile.name }}</a>
        </p>
      </div>    
    {% endif %}
  {% endfor %}
</div>
<hr>

{% else %}

<br>

| Who are they | When were they here | Where they went |
| :------------- |:-------------| :-----------|
| Nicholas Cimaszewski| Undergraduate (2021) | |
| Martynas Snarskis| Undergraduate (2021) | |
| Linghao Xu| Masters Student (2021) | Ph.D. at Ruben Coen Cagli's lab|
| [Richard Lange](http://boxandarrowbrain.com) | Graduate Student (2020) | Postdoc at Konrad Kording's Lab |
| Ankani Chattoraj | Graduate Student (2022)| Data Research Scientist


{% endif %}
{% endfor %}
