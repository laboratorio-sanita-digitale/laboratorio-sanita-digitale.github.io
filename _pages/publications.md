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

{% assign theses_by_year = site.data.thesis | group_by: "year" %}
{% for year in theses_by_year %}
## {{ year.name }}
{% for thesis in year.items %}
- *{{ thesis.author }}* - **{{ thesis.title }}** - {{ thesis.degree }} - {{ thesis.course }}
{% endfor %}
{% endfor %}