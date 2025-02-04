---
permalink: /publications/
title: "Pubblicazioni e Tesi"
excerpt: ""
modified: 2022-08-31T10:51:37+01:00
---
{% include base_path %}

# Pubblicazioni


{% assign publications_by_year = site.data.publications | group_by: "year" %}
{% for year in publications_by_year %}
## {{ year.name }}
{% for publication in year.items %}
- *{{ publication.author }}* - **{{ publication.title }}** - 
    {% if publication.type == "inproceedings" %}
        {{ publication.booktitle }}
    {% elsif publication.type == "article" %}
        {{ publication.journal }}
    {% endif %}
    {% if publication.url %}
        [Link]({{ publication.url }})
    {% endif %}
{% endfor %}
{% endfor %}

# Tesi

Una raccolta delle tesi sviluppate nel contesto della collaborazione del Laboratorio Sanità Digitale.

{% assign theses_by_year = site.data.thesis | group_by: "year" %}
{% for year in theses_by_year %}
## {{ year.name }}
{% for thesis in year.items %}
- *{{ thesis.author }}* - **{{ thesis.title }}** - {{ thesis.degree }} - {{ thesis.course }}
{% endfor %}
{% endfor %}