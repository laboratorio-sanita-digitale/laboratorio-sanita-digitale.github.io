---
permalink: /projects/
title: "Attività e Progetti"
excerpt: ""
classes: labsd-wide justified-text
---

{% include base_path %}

# Attività e Progetti

L'elenco dei principali progetti realizzati nell'ambito delle attività del laboratorio.

{% for project in site.data.projects %}

  <div class="labsd-project-card">

    <div class="labsd-project-card__content">
      <h2>{{ project.title }}</h2>

      <p class="labsd-project-card__subtitle">
        {{ project.description }}
      </p>

      <a href="{{ project.permalink }}" class="btn btn--primary">
        Scopri il progetto
      </a>
    </div>

    <div class="labsd-project-card__logo">
      <img src="{{ project.logo }}" alt="Logo {{ project.title }}">
    </div>

  </div>

{% endfor %}

