---
permalink: /available-projects/
title: "Proposte per tesi e tirocini"
excerpt: ""
---
{% include base_path %}

Una raccolta delle proposte per tesi e tirocini attivabili

{% for project in site.data.available-projects %}
  <div class="project-card">
    <h2>{{ project.title }}</h2>
    <p>{{ project.abstract }}</p>

    <h3>Attività principali</h3>
    <ul>
      {% for activity in project.main_activities %}
        <li>{{ activity }}</li>
      {% endfor %}
    </ul>
  </div>
{% endfor %}
