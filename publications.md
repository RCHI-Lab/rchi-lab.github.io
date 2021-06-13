---
layout: page
title: Publications
---

Our lab begins in Fall 2021! Publications and preprints from our group will show up here.

# Preprints

# Publications

<table cellpadding="10" width="100%">
{% for pub in site.data.publications %}
    <tr>
        <td width="250" height="100">
            <img src="{{pub.image}}" img width="250">
            <!--{% if pub.note %}
                <img src="{{ pub.image }}" img width="250">
            {% else %}
                <img src="" img width="250">
            {% endif %}-->
        </td>
        <td><a href="{{pub.pdf}}">{{pub.title}}</a><br>
            {{pub.authors}}<br>
            <div id="bib{{pub.id}}" style="display:none">
                <blockquote>
                    <pre>{{pub.bibtex}}</pre>
                </blockquote>
            </div>
            <div id="abs{{pub.id}}" style="display:none">
                <blockquote>
                    {{pub.abstract}}
                </blockquote>
            </div>
            <em>{{pub.venue}}</em>, {{pub.year}}
            <div style="font-size:small">
                <em>
                    {% if pub.projectpage %}
                        <a href="{{pub.projectpage}}">[Project Page]</a>
                    {% endif %}
                    {% if pub.code %}
                        <a href="{{pub.code}}">[Code]</a>
                    {% endif %}
                    {% if pub.bibtex %}
                        <a href="javascript:copy(div{{pub.id}}, bib{{pub.id}})">[Bibtex]</a>
                    {% endif %}
                    {% if pub.abstract %}
                        <a href="javascript:copy(div{{pub.id}}, abs{{pub.id}})">[Abstract]</a>
                    {% endif %}
                    {% if pub.pdf %}
                        <a href="{{pub.pdf}}">[PDF]</a>
                    {% endif %}
                </em>
            </div>
            <div id="div{{pub.id}}"></div>
            <br>
        </td>
    </tr>
{% endfor %}
</table>