---
layout: page
title: Members
slim: true
---


<div class="row">
    {% for big_group in site.data.members %}
        <div class="w-100"></div>
        <h1> {{big_group.name}} </h1>
        <div class="w-100"></div>
        {% for group in big_group.list %}
            {% if group.list.size > 0 %}
                {% if group.name %}
                    <div class="w-100"></div>
                    {% if group.website %}
                        <a target="_blank" href="{{group.website}}"><h2>{{ group.name }}</h2></a>
                    {% else %}
                        <h2>{{ group.name }}</h2>
                    {% endif %}
                    <div class="w-100"></div>
                {% endif %}
                {% if group.full %}
                  <div class="row">
                      {% for member in group.list %}
                          <div class="col-xl-3 col-lg-3 col-md-4 text-center col-sm-6 col-xs-6">
                              <a target="_blank" href="{{member.website}}">
                                  <img class="img-circle" src="{{member.image}}" alt="{{member.alt}}">
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

