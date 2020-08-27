---
title: People
permalink: /people/
---

{% assign people_sorted = site.people | sort: 'joined' %}
{% assign role_array = "pi|gradstudents|undergrad researchers" | split: "|" %}

{% for role in role_array %}

{% assign people_in_role = people_sorted | where: 'position', role %}

<!-- Skip section if there's nobody -->
{% if people_in_role.size == 0 %}
  {% continue %}
{% endif %}

<div class="pos_header">
 {% elsif role == 'pi' %}
<h3>교수</h3>
 {% elsif role == 'pi' %}
<h3>석·박사 연구원</h3>
 {% elsif role == 'gradstudents' %}
<h3>학부 연구원</h3>
 {% elsif role == 'undergrad researchers' %}
{% endif %}
</div>


{% endif %}
{% endfor %}
