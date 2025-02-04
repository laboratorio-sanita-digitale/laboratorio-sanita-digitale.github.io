---
permalink: /thesis/
title: "Tesi"
excerpt: ""
---
{% include base_path %}

# Tesi

Una raccolta delle tesi sviluppate nel contesto della collaborazione del Laboratorio Sanità Digitale.

{% assign theses_by_year = site.data.thesis | group_by: "year" %}
{% for year in theses_by_year %}
## {{ year.name }}
{% for thesis in year.items %}
- *{{ thesis.author }}* - **{{ thesis.title }}** - {{ thesis.degree }} - {{ thesis.course }}
{% endfor %}
{% endfor %}