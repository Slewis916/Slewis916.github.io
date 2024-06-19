---
layout: default
title: "Projects"
permalink: /projects/
---


<ul>
  {% for project in site.projects %}
    <li>
      <a href="{{ project.url }}">{{ project.title }}</a> - {{ project.description }}
    </li>
  {% endfor %}
</ul>
