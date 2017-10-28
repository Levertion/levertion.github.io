---
title: Translation Support; Optional Resource Pack
categories: 
  - resource_packs
excerpt: "How to support translations, without requiring a resource pack (mostly)"
tags: 
  - Vanilla
  - Mapmaking
  - Translation
  - Resource Packs
  - Minecraft
---
## Translation support without a mandatory resource pack

When developing maps, it is good to make sure that your map has full support for translations to allow for players anywhere to enjoy your map.  
Minecraft does have an in-game way to translate (most) in-game strings. However, to use this in a map normally requires a resource pack. Unfortunately, making the players of your map use the resource pack is quite hard. You can confirm upon login that they are using it (as first shown by [The Redstone Scientist](https://www.youtube.com/channel/UCf9NPB_CV1tXoh6mdryvHzg) in [this video](https://www.youtube.com/watch?v=72WkM1fKGPA)), but if they logout they could remove it. Server resource packs can be denied too, so that is no solution.  
Therefore, where it can be avoided, it always seems best to make resource packs optional  

## Avoiding this
However, if you don't use a resource pack, it seems inevitable that you will have to not support translations.  
However, the order of translation checks is quite important. What happens when a translation requested is effectively (caching is used to avoid the large numbers of file checks):  
1. Check the `.lang` file of each resource pack in the RP order of your selected language for that translation, with the built-in language being the last.
2. Check the `en-us` file of each RP for the translation
3. **Fallback onto the translation key**  

The last point is what allows this to be possible:  
> Fallback onto the translation key  

This means that the translation key is the default value, so you could write every text as your translation key.  
This means instead of using the `"text":` component of JSON text components, you use `"translate":`. That's it.
The only place where you must be careful is in books, where the book must be created by a command to use text components, and the json formatting must be escaped, and each item needs to use locName (which you should anyway as it makes them not italic)

## Example  
For example, imagine that you have an intro sentence. Your original text component would look like this:
```JSON
{"text":"Hello, welcome to this map"}
```
To allow translation, you would change this to:
```JSON
{"translate":"Hello, welcome to this map"}
```
To translate it, in the resource pack (which only needs to be used by the people who want the map in it's not default language), you would type:
```
Hello, welcome to this map=Hallo, willkommen als dieser Welt  
```

## Limitations
It is currently impossible to translate lore and entity names. Other than that, most other strings are translatable, and there are plans to move over to JSON text components for everything