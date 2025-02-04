---
permalink: /publications/
title: "Pubblicazioni e Tesi"
excerpt: ""
modified: 2022-08-31T10:51:37+01:00
---
{% include base_path %}

# Pubblicazioni



# Tesi

Una raccolta delle tesi sviluppate nel contesto della collaborazione del Laboratorio Sanità Digitale.

{% assign theses = site.data.thesis %}

{% for year in theses | group_by: "year" %}
## {{ year.name }}

{% for thesis in year.items %}
- *{{ thesis.title }}*, **{{ thesis.author }}** - {{ thesis.degree }}, {{ thesis.course }}
{% endfor %}

{% endfor %}
