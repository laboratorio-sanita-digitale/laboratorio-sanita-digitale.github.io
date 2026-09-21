---
permalink: /publications/thesis/
title: "Tesi di Laurea"
excerpt: ""
classes: labsd-wide justified-text
---

{% include base_path %}

# Tesi di Laurea

Una raccolta delle tesi sviluppate nel contesto della collaborazione del Laboratorio Sanità Digitale.

{% assign theses_by_year = site.data.thesis | group_by: "year" %}
{% for year in theses_by_year %}
## {{ year.name }}
{% for thesis in year.items %}
- *{{ thesis.author }}* - **{{ thesis.title }}** - {{ thesis.degree }} - {{ thesis.course }}
{% endfor %}
{% endfor %}