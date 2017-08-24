---
title: Home
permalink: /index.html
tags: ["example"]
---
# Introduction  
On this website I will be showing my various minecraft creations and utilities. Some of these will be useful for map-making, or video creation.

# Examples  
---
{%- for example in site.pages -%}
{%- if example.is_example -%}
# [{{example.title}}]({{example.url}})  {%-if example.supported_version -%}For {{- example.supported_version -}}{%- endif -%}
{%- if example.description -%}
  {{ example.description }}
{%- endif -%}
---
{%- endif -%}
{%- endfor -%}
