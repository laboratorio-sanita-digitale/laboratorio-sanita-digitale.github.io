---
permalink: /available-projects/
title: "Proposte per tesi e tirocini"
excerpt: ""
---
{% include base_path %}

Una raccolta delle proposte per tesi e tirocini attivabili

---
permalink: /available-projects/
title: "Proposte per tesi e tirocini"
excerpt: ""
---
{% include base_path %}

Una raccolta delle proposte per tesi e tirocini attivabili

{% for project in site.data.available-projects %}

<table>
  <tbody>

    <tr>
      <td><strong>Titolo</strong></td>
      <td>{{ project.title }}</td>
    </tr>

    <tr>
      <td><strong>Area</strong></td>
      <td>{{ project.area }}</td>
    </tr>

    <tr>
      <td><strong>Abstract</strong></td>
      <td>{{ project.abstract }}</td>
    </tr>

    <tr>
      <td><strong>Attività principali</strong></td>
      <td>
        <ul>
          {% for activity in project["main-activities"] %}
            <li>{{ activity }}</li>
          {% endfor %}
        </ul>
      </td>
    </tr>

  </tbody>
</table>

<br><br>

{% endfor %}
