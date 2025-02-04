---
permalink: /publications/
title: "Pubblicazioni"
excerpt: ""
---
{% include base_path %}

# Pubblicazioni

{% assign publications_by_year = site.data.publications | group_by: "year" %}
{% for year in publications_by_year %}
## {{ year.name }}
{% for publication in year.items %}
- *{{ publication.author }}* - **{{ publication.title }}** - {% if publication.type == "inproceedings" %}{{ publication.booktitle }}{% elsif publication.type == "article" %}{{ publication.journal }}{% endif %}{% if publication.url %} ([Link]({{ publication.url }})){% endif %}
{% endfor %}
{% endfor %}