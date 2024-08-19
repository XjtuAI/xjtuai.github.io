---
title: Members
permalink: /people/
---

{% assign people_sorted = site.people| sort: 'joined' %}
{% assign role_array = "sci" | split: "|" %}

{% for role in role_array %}

{% assign people_in_role = people_sorted | where: 'position', role %}

<!-- Skip section if there's nobody -->
{% if people_in_role.size == 0 %}
  {% continue %}
{% endif %}

<div class="pos_header">
{% if role == 'sci' %}
<h3>Researchers</h3>
{% endif %}
</div>


<hr>

{% else %}



{% endif %}
{% endfor %}
