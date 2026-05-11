---
permalink: /manifesto/scientific-committee/
title: "Attuale Comitato Scientifico"
excerpt: ""
---
{% include base_path %}

# Membri del comitato scientifico in carica

{% assign people_by_institution = site.data.scientific-committee | group_by: "institution" %}

{% for institution_group in people_by_institution %}
  <h2>{{ institution_group.name }}</h2>

  <div class="people-list">
    {% for person in institution_group.items %}
      <div class="person-card">
        <h3>{{ person.title }} {{ person.name }} {{ person.surname }}</h3>

        <p>{{ person.role }}</p>

        {% if person.annotations and person.annotations != "--" %}
          <p>
            <em>{{ person.annotations }}</em>
          </p>
        {% endif %}
      </div>
    {% endfor %}
  </div>
{% endfor %}
