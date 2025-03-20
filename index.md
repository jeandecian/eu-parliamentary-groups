---
layout: default
---

<h1>{{ site.title }}</h1>
<table class="table table-hover table-sm">
  <thead>
    <tr>
      <th scope="col">Member State</th>
      <th scope="col">Lower House</th>
      <th scope="col">Session</th>
      <th scope="col" colspan="9">Groups</th>
      <th scope="col">Date</th>
    </tr>
  </thead>
  <tbody class="table-group-divider">
    {% for parliament in site.data.parliaments %}
    <tr>
      <th scope="row">{{ parliament.member-state }}</th>
      <td>{{ parliament.lower-house }}</td>
      <td>{{ parliament.session }}</td>
      {% for group in parliament.groups %}
      <td
        {%
        if
        group.color
        %}
        style="background-color: {{ group.color }}; color: white;"
        {%
        endif
        %}
      >
        {{ group.name }} ({{ group.number-of-mps }})
      </td>
      {% endfor %}
      <td>{{ parliament.date }}</td>
    </tr>
    {% endfor %}
  </tbody>
</table>
<h3>Sources</h3>
<ul>
  {% for source in site.data.sources %}
  <li>
    <a class="text-decoration-none" href="{{ source.url }}" target="_blank"
      >{{ source.title }}</a
    >
    ({{ source.date }})
  </li>
  {% endfor %}
</ul>
