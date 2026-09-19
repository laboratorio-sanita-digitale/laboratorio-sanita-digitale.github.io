---
permalink: /publications/scientific-works/
title: "Pubblicazioni Scientifiche"
excerpt: ""
classes: labsd-wide justified-text
---
{% include base_path %}

# Pubblicazioni Scientifiche

{% assign publications_by_year = site.data.publications | group_by: "year" %}
{% for year in publications_by_year %}
## {{ year.name }}
{% for publication in year.items %}
- *{{ publication.author }}* - **{{ publication.title }}** - {% if publication.type == "inproceedings" %}{{ publication.booktitle }}{% elsif publication.type == "article" %}{{ publication.journal }}{% endif %}{% if publication.url %} ([Link]({{ publication.url }})){% endif %}
{% endfor %}
{% endfor %}