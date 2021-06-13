---
layout: page
title: Publications
---

Our lab begins in Fall 2021! Publications and preprints from our group will show up here.

# Preprints

# Publications

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
                        <!--<a href="javascript:copy(div{{pub.id}},bib{{pub.id}})">[Bibtex]</a>-->
                        <!--<a href="javascript:showhide(bib{{pub.id}})">[Bibtex]</a>-->
                        <!--<a href="javascript:copyDiv('bib{{pub.id}}','div{{pub.id}}')">[Bibtex]</a>-->
                        <!--<a href="javascript:copyDiv('bib2','div2')">[Bibtex]</a>-->
                        <!--<a href="javascript:alert('You clicked!')">My link</a>-->
                        <!--<a href="javascript:myFunction('You clicked!')">My link</a>-->
                        <!-- <a href="javascript:showhide('bib2')">Bib2</a> -->
                        <a href="javascript:showhide('bib{{pub.id}}')">[Bibtex]</a>
                    {% endif %}
                    {% if pub.abstract %}
                        <!--<a href="javascript:copy('div{{pub.id}}','abs{{pub.id}}')">[Abstract]</a>-->
                        <!--<a href="javascript:showhide(abs{{pub.id}})">[Abstract]</a>-->
                        <!--<a href="javascript:copy(div2,bib2)">[Bibtex]</a>-->
                        <!--<a href="javascript:alert('{{pub.id}}')">My link</a>-->
                        <a href="javascript:showhide('abs{{pub.id}}')">[Abstract]</a>
                    {% endif %}
                    {% if pub.video %}
                        <a href="{{pub.video}}">[Video]</a>
                    {% endif %}
                    {% if pub.pdf %}
                        <a href="{{pub.pdf}}">[PDF]</a>
                    {% endif %}
                </em>
                <div id="bib{{pub.id}}" style="display:none">
                    <br>
                    {{pub.bibtex}}
                </div>
                <div id="abs{{pub.id}}" style="display:none">
                    <br>
                    {{pub.abstract}}
                </div>
            </div>
            <br>
        </td>
    </tr>
{% endfor %}
</table>


