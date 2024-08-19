---
title: People
permalink: /people/
---

{% assign people_sorted = site.people %}

{% for profile in people_sorted %}
  <div>
    <p>{{ profile.name }} - {{ profile.position }}</p>
  </div>
{% endfor %}
