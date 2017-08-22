---
title: Home
permalink: /index.html
tags: example
---
# Introduction  
On this website I will be showing my various minecraft creations and utilities. Some of these will be useful for map-making, or video creation.

# Examples  
{% for example in site.tags.example%}
  {{example}}
{%endfor%}
