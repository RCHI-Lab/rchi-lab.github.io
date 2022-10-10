---
layout: page
title: Members
slim: true
---


<div class="row">
    {% for big_group in site.data.members %}
        <h1> {{big_group.name}} </h1>
        {% for group in big_group.list %}
            {% if group.list.size > 0 %}
                {% if group.name %}
                    <h2>{{ group.name }} Test</h2>
                {% endif %}
                {% if group.full %}
                  <div class="row">
                      {% for member in group.list %}
                          <div class="col-xl-3 col-lg-3 col-md-4 text-center col-sm-6 col-xs-6">
                              <a target="_blank" href="{{member.website}}">
                                  <img class="img-responsive img-circle" src="{{member.image}}" alt="{{member.alt}}">
                              </a>
                              {% if member.website %}
                                  <a target="_blank" href="{{member.website}}">{{member.name}}</a>
                              {% else %}
                                  {{member.name}}
                              {% endif %}
                              <!--{% if member.coadvisor %}
                                  <br>Co-advised by <a target="_blank" href="{{member.coadvisorweb}}">{{member.coadvisor}}</a>
                              {% endif %}-->
                          </div>
                      {% endfor %}
                  </div>
                {% else %}
                   <ul>
                        {% for member in group.list %}
                            {% if member.website %}
                                <li><a target="_blank" href="{{member.website}}"> {{member.name}} </a></li>
                            {% else %}
                                <li><a> {{member.name}} </a></li>
                            {% endif %}
                        {% endfor %}
                    </ul>
                {% endif %}
                <br>
            {% endif %}
        {% endfor %}
    {% endfor %}
</div>

