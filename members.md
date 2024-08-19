---
title: Members
permalink: /members/
---

{% assign people_sorted = site.members | sort: 'joined' %}
{% assign role_array = "sci|fac|ap|adjunctprofessor|postdoc|phd|grad|alumni" | split: "|" %}

{% for role in role_array %}

{% assign people_in_role = people_sorted | where: 'position', role %}

<!-- Skip section if there's nobody -->
{% if people_in_role.size == 0 %}
  {% continue %}
{% endif %}

<div class="pos_header">
{% if role == 'sci' %}
<h3>Researchers</h3>
{% if role == 'fac' %}
<h3>Faculties</h3>
 {% elsif role == 'adjunctprofessor' %}
<h3>Adjunct Professors</h3>
 {% elsif role == 'ap' %}
<h3>Assistant Professor</h3>
 {% elsif role == 'postdoc' %}
<h3>Postdoc</h3>
 {% elsif role == 'phd' %}
<h3>Ph.D Students</h3>
 {% elsif role == 'grad' %}
<h3>Graduate Students</h3>
 {% elsif role == 'researchstaff' %}
<h3>Research Staff</h3>
 {% elsif role == 'visiting' %}
<h3>Visiting Scholars</h3>
 {% elsif role == 'others' %}
<h3>Honorary Members</h3>
 {% elsif role == 'alumni' %}
<h3>Alumni</h3> 
{% endif %}
</div>


<hr>

{% else %}



{% endif %}
{% endfor %}
