---
layout: page
title: Publications
---

Our lab begins in Fall 2021! Publications from our group will show up here.

{% for pub in site.data.publications %}
    <p>
        <a href="{{ pub.link.url }}">{{ pub.title }}</a>
        <br/>{{ pub.authors }}
        <br/><em>{{ pub.venue }}</em>&nbsp;{{ pub.year }}.
        {% if pub.note %}
            <br/><strong>{{ pub.note }}</strong>
        {% endif %}
    </p>
{% endfor %}
