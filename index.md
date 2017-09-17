---
title: Home
permalink: /index.html
tags: ["example"]
---
# About  
On this website I will be showing my various minecraft creations and utilities. Some of these will be useful for map-making, or video creation.

# Examples  
---
{% assign examples = (site.posts | where: "is_example", "true") %}
{% for example in examples %}
## [{{example.title}}]({{example.url | absolute_url }})  
{%if example.supported_versions %}#### For {{example.supported_versions}} {% endif %}
{% if example.description %}
  {{ example.description }}
{% endif %}
---
{% endfor %}
