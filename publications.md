---
layout: page
title: Publications
---

The most accurate list of publications can be found on [Google Scholar](https://scholar.google.com/citations?user=wElkTtIAAAAJ&hl=en)

<script>
function showhide(d) {
  var x = document.getElementById(d);
  if (x.style.display === "none") {
    x.style.display = "block";
  } else {
    x.style.display = "none";
  }
}
</script>

{% assign has_preprints = false %}
{% for pub in site.data.publications %}
    {% if pub.type == "preprint" %}
        {% assign has_preprints = true %}
        {% break %}
    {% endif %}
{% endfor %}

{% if has_preprints == true %}
# Preprints
<table cellpadding="10" width="100%">
{% for pub in site.data.publications %}
    {% if pub.type == "preprint" %}
        {% assign authors = {{pub.authors}} | split: ", " %}
        <tr>
            <td width="200" height="100">
                <img src="{{pub.image}}" img width="250">
            </td>
            <td><h6><a href="{{pub.pdf}}">{{pub.title}}</a></h6>
                <div style="line-height:50%;">
                    <br>
                </div>
                <div style="font-size:medium">
                    {% for author in authors %}
                        {% if forloop.index == authors.size %}
                            <nobr>{{ author }}</nobr>
                        {% else %}
                            <nobr>{{ author }},</nobr>
                        {% endif %}
                    {% endfor %}<br>
                    <em>{{pub.venue}}</em>, {{pub.year}}
                    {% if pub.awards %}
                        <b> {{pub.awards}}</b>
                    {% endif %}
                    <br>
                </div>
                <div style="line-height:50%;">
                    <br>
                </div>
                <div style="font-size:small">
                    <em>
                        {% if pub.pdf %}
                            <a href="{{pub.pdf}}">[PDF]</a>
                        {% endif %}
                        {% if pub.projectpage %}
                            <a href="{{pub.projectpage}}">[Project Page]</a>
                        {% endif %}
                        {% if pub.code %}
                            <a href="{{pub.code}}">[Code]</a>
                        {% endif %}
                        {% if pub.bibtex %}
                            <a href="javascript:showhide('bib{{pub.id}}')">[Bibtex]</a>
                        {% endif %}
                        {% if pub.abstract %}
                            <a href="javascript:showhide('abs{{pub.id}}')">[Abstract]</a>
                        {% endif %}
                        {% if pub.video %}
                            <a href="{{pub.video}}">[Video]</a>
                        {% endif %}
                    </em>
                    <div id="bib{{pub.id}}" style="display:none">
                        <br>
                        <blockquote>
                            <div style="white-space: pre-wrap;">{{pub.bibtex}}</div>
                        </blockquote>
                    </div>
                    <div id="abs{{pub.id}}" style="display:none">
                        <br>
                        {{pub.abstract}}
                    </div>
                </div>
                <br>
            </td>
        </tr>
    {% endif %}
{% endfor %}
</table>
{% endif %}


{% assign has_pubs = false %}
{% for pub in site.data.publications %}
    {% if pub.type != "preprint" %}
        {% assign has_pubs = true %}
        {% break %}
    {% endif %}
{% endfor %}

{% if has_pubs == true %}
{% if has_preprints == true %}
# Peer-Reviewed Publications
{% endif %}

<table cellpadding="10" width="100%">
{% for pub in site.data.publications %}
    {% if pub.type != "preprint" %}
        {% assign authors = {{pub.authors}} | split: ", " %}
        <tr>
            <td width="200" height="100">
                <img src="{{pub.image}}" img width="250">
            </td>
            <td><h6><a href="{{pub.pdf}}">{{pub.title}}</a></h6>
                <div style="line-height:50%;">
                    <br>
                </div>
                <div style="font-size:medium">
                    {% for author in authors %}
                        {% if forloop.index == authors.size %}
                            <nobr>{{ author }}</nobr>
                        {% else %}
                            <nobr>{{ author }},</nobr>
                        {% endif %}
                    {% endfor %}<br>
                    <em>{{pub.venue}}</em>, {{pub.year}}
                    {% if pub.awards %}
                        <b> {{pub.awards}}</b>
                    {% endif %}
                    <br>
                </div>
                <div style="line-height:50%;">
                    <br>
                </div>
                <div style="font-size:small">
                    <em>
                        {% if pub.pdf %}
                            <a href="{{pub.pdf}}">[PDF]</a>
                        {% endif %}
                        {% if pub.projectpage %}
                            <a href="{{pub.projectpage}}">[Project Page]</a>
                        {% endif %}
                        {% if pub.code %}
                            <a href="{{pub.code}}">[Code]</a>
                        {% endif %}
                        {% if pub.bibtex %}
                            <a href="javascript:showhide('bib{{pub.id}}')">[Bibtex]</a>
                        {% endif %}
                        {% if pub.abstract %}
                            <a href="javascript:showhide('abs{{pub.id}}')">[Abstract]</a>
                        {% endif %}
                        {% if pub.video %}
                            <a href="{{pub.video}}">[Video]</a>
                        {% endif %}
                        {% if pub.news %}
                            <a href="{{pub.news}}">[In The News]</a>
                        {% endif %}
                    </em>
                    <div id="bib{{pub.id}}" style="display:none">
                        <br>
                        <blockquote>
                            <div style="white-space: pre-wrap;">{{pub.bibtex}}</div>
                        </blockquote>
                    </div>
                    <div id="abs{{pub.id}}" style="display:none">
                        <br>
                        {{pub.abstract}}
                    </div>
                </div>
                <br>
            </td>
        </tr>
    {% endif %}
{% endfor %}
</table>
{% endif %}
