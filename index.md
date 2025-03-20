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
      <th scope="col">Seats</th>
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
        {{ group.name }} {% if group.number-of-mps %} ({{ group.number-of-mps
        }}) {% endif %}
      </td>
      {% endfor %} {% if parliament.seats %} {% assign total_mps = 0 %} {% for
      group in parliament.groups %} {% assign total_mps = total_mps | plus:
      group["number-of-mps"] %} {% endfor %}
      <td>{{ total_mps }} / {{ parliament.seats }}</td>
      {% endif %}
      <td>
        <a
          class="text-decoration-none"
          href="{{ parliament.source-url }}"
          target="_blank"
          >{{ parliament.date }}</a
        >
      </td>
    </tr>
    {% endfor %}
  </tbody>
</table>
