---
layout: page
title: Members
---


<div class="row">
    {% for big_group in site.data.members %}
        <h1> {{big_group.name}} </h1>
        {% for group in big_group.list %}
            {% if group.list.size > 0 %}
                {% if group.name %}
                    <h2>{{ group.name }}</h2>
                {% endif %}
                {% if group.full %}
                  <div class="row member-row">
                      {% for member in group.list %}
                          <div class="col-xl-2 col-lg-2 col-md-3 text-center col-sm-6 col-xs-6 member-col">
                              <a target="_blank" href="{{member.website}}">
                                  <img class="img-responsive" src="{{member.image}}">
                              </a>
                              <a target="_blank" href="{{member.website}}">
                                  {{member.name}}
                              </a>
                          </div>
                      {% endfor %}
                  </div>
                {% else %}
                    <ul>
                        {% for member in group.list %}
                            {% if member.website %}
                                <li><a href="{{member.website}}"> {{member.name}} </a></li>
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

