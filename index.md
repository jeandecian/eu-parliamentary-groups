---
layout: default
---

<h1>{{ site.title }}</h1>
<table class="table table-hover table-sm">
  <thead>
    <tr>
      <th scope="col">Member State</th>
      <th scope="col">Lower House</th>
    </tr>
  </thead>
  <tbody class="table-group-divider">
    {% for parliament in site.data.parliaments %}
    <tr>
      <th scope="row">{{ parliament.member-state }}</th>
      <td>{{ parliament.lower-house }}</td>
    </tr>
    {% endfor %}
  </tbody>
</table>
