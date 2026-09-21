---
permalink: /available-topics/
title: "Temi d'interesse"
excerpt: ""
classes: labsd-wide
---

{% include base_path %}

# Temi d'interesse

Temi e contesti di interesse dai quali possono nascere tesi, tirocini, progetti e attività di ricerca, sviluppati con il supporto di ricercatori e professionisti esperti del dominio sanitario.

<a id="top"></a>

<div class="projects-page-layout">
  <div class="projects-page-nav">
    <h3 class="projects-page-nav-title">Aree Tematiche</h3>
    <div class="projects-page-list">
      <ul>
        {% for area in site.data.available_topics_areas %}
          <li>
            <a href="#area-{{ area.id }}">{{ area.title }}</a>
          </li>
        {% endfor %}
      </ul>
    </div>
  </div>
  <div class="projects-page-content">
    {% for area in site.data.available_topics_areas %}
      <div id="area-{{ area.id }}" class="project-area-heading">
        <h2>{{ area.title }}</h2>
      </div>
      {% for topic in site.data.available_topics %}
        {% if topic.areas contains area.id %}
          <a id="{{ topic.id }}"></a>
          <div class="project-id-ribbon">{{ topic.id }}</div>
          <table>
            <tbody>
              <!--<tr>
                <td><strong>ID Progetto</strong></td>
                <td>{{ topic.id }}</td>
              </tr>-->
              <tr>
                <td>Titolo</td>
                <td>{{ topic.title }}</td>
              </tr>
              <tr>
                <td>Area</td>
                <td>
                  {% for topic_area_id in topic.areas %}
                    {% assign topic_area = site.data.available_topics_areas | where: "id", topic_area_id | first %}
                    <span class="project-area-tag">{{ topic_area.title }}</span>
                  {% endfor %}
                </td>
              </tr>
              <tr>
                <td>Abstract</td>
                <td>{{ topic.abstract }}</td>
              </tr>
              <tr>
                <td>Attività principali</td>
                <td>
                  <ul>
                    {% for activity in topic["main-activities"] %}
                      <li>{{ activity }}</li>
                    {% endfor %}
                  </ul>
                </td>
              </tr>
            </tbody>
          </table>
        {% endif %}
      {% endfor %}
      <p class="project-back-top">
        <a href="#top">↑ Torna su</a>
      </p>
    {% endfor %}
  </div>
</div>
