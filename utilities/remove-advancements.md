---
title: Remove Vanilla Advancements
is_example: True
description: "Two methods of removing vanilla advancements, and how to do it yourself"
supported_version_internal: [12]
supported_version: "1.12-1.12.1"
permalink: /utilities/remove-advancements.html
---
For a lot of Minecraft content apart from lets plays, the vanilla advancements take away from the professionalism rather than add to the experience of the content. This is especially important for map-making and tutorial video production, when it removes from immersion.  
Luckily, vanilla Minecraft has multiple methods to remove these advancements.    
## Method 1 (Overwrite all)
### [Download](https://github.com/Levertion/remove-advancements/releases/download/Overwite-allv1.1/remove-advancements.zip)    
### Explanation
*This is my preferred method:*  
For each advancement, it replaces the content with:  
```json
{"criteria":{
  "impossible":{
    "trigger":"minecraft:impossible"
}}}
```
This is because when Minecraft detects that there is an advancement with the same filename as one of the vanilla ones in the word, it uses that one instead. The above JSON would create

## Method 2 (Create invalid roots)
