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

{% for thesis in site.data.thesis %}
- **{{ thesis.year }}** - *{{ thesis.author }}* - **{{ thesis.title }}** - {{ thesis.degree }} - {{ thesis.course }}
{% endfor %}