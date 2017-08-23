---
title: Home
permalink: /index.html
tags: ["example"]
---
# Introduction  
On this website I will be showing my various minecraft creations and utilities. Some of these will be useful for map-making, or video creation.

# Examples  
[example1](example1.md)
hi 1  
{% for example in site.pages %}
{{example.title}}
{% unless example.url==page.url %}
{{example}}
{% endunless %}
{% if example.asExample %}
# [{{example.title}}]({{example.url}})
{% if example.description %}
  {{ example.description }}
{% endif %}
{% endif %}
{% endfor %}
