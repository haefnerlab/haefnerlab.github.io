---
title: Publication
permalink: /publication3/
---

All info here: [google scholar citations profile](https://scholar.google.com/citations?user=Xd_w2fIAAAAJ&hl).

<ul>
    {% assign sorted = site.data.publications | sort: 'date' | reverse %}
    {% for item in sorted %}
    <li>{{ item.title }}</li>
    {% endfor %}
</ul>