---
title: Home
permalink: /index.html
tags: ["example"]
---
# Introduction  
On this website I will be showing my various minecraft creations and utilities. Some of these will be useful for map-making, or video creation.

# Examples  
---
{% assign examples = (site.pages | where: "is_example", True) %}
{% for example in examples %}
# [{{example.title}}]({{example.url}}) {%if example.supported_versions %} For {{example.supported_versions}} {% endif %}
{% if example.description %}
  {{ example.description }}
{% endif %}
---
{% endfor %}
