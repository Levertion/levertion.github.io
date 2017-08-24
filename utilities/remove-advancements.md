---
title: Remove Vanilla Advancements
is_example: "True"
description: "Two methods of removing vanilla advancements, and how to do it yourself"
supported_versions_internal: [12]
supported_version: "1.12(.1)"
permalink: /utilities/remove-advancements.html
---
For a lot of Minecraft content apart from the vanilla survival experience, the vanilla advancements take away from the professionalism rather than add to the experience of the content. This is especially important for map-making and tutorial video production, when it removes from immersion because of unneeded toasts.  
Luckily, vanilla Minecraft has multiple methods to remove these advancements. This also stops the gaining of recipes when collecting items.   
## Method 1 (Overwrite all)
### [Download](https://github.com/Levertion/remove-advancements/releases/download/Overwite-allv1.1/remove-advancements.zip)    
#### Installation  
Extract the zip from the link above into your world's data folder.  
### Explanation
*This is my preferred method:*  
For each advancement, it replaces the content with:  
```json
{"criteria":{
  "impossible":{
    "trigger":"minecraft:impossible"
}}}
```
This is because when Minecraft detects that there is an advancement with the same filename as one of the vanilla ones in the word, it uses that one instead. The above json creates an advancement with no display data, so it does not have an icon or display a toast.  
The code used to generate the folder can be found [here](https://github.com/Levertion/remove-advancements/blob/overwrite-all/noadvancements.py). This is a [python](https://www.python.org/) script mostly based on [this stackoverflow answer](https://stackoverflow.com/a/19308592) and extracted the original files with [7-zip](http://www.7-zip.org/) from the Minecraft 1.12 client jar  
## Method 2 (Create invalid roots)
This method is documented [here](https://www.reddit.com/r/MinecraftCommands/comments/6fvcdj/empty_advancements/dim8lq2/?st=j6qkunj1&sh=b85d431d) by [/u/makluss](https://www.reddit.com/user/Mlakuss) on Reddit, as well as a discussion of the advantages and disadvantages of both methods.  
