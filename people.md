---
title: People
permalink: /people/
---

{% assign people_sorted = site.people | sort: 'joined' %}
{% assign role_array = "pi|postdoc|gradstudent|researchstaff|visiting|others|alumni" | split: "|" %}

{% for role in role_array %}

{% assign people_in_role = people_sorted | where: 'position', role %}

<!-- Skip section if there's nobody -->
{% if people_in_role.size == 0 %}
  {% continue %}
{% endif %}

<div class="pos_header">
{% if role == 'postdoc' %}
<h3>석·박사 연구원</h3>
 {% elsif role == 'pi' %}
<h3>교수</h3>
 {% elsif role == 'gradstudent' %}
<h3>학부 연구원</h3>
{% endif %}
</div>

{% endfor %}
