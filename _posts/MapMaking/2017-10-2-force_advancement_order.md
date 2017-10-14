---
title: Force an Advancement to follow another
excerpt: "How to force one advancement to only be obtainable after another already has been"
categories: 
  - Advancements
tags:
  - Vanilla 
  - Minecraft
  - Advancements
  - Mapmaking
---
## How to force one Advancement to follow another  

When using advancements, it can be useful to require one to follow another, in the same way that the old achievements did.  
This is possible, using the `<criterion>` argument of the `advancement` command.
## In practise  
### Advancement setup
To add this functionality, your second advancement should have an additional criterion (in the `criteria` key). For the sake of this tutorial, it will be called `"follow"`. This needs to be an `impossible` trigger, as shown below:
```json
{
  "trigger":"minecraft:impossible"
}
```
----------
If using a custom requirements list, you will also need to make the `"follow"` criteria be required. This can be done by putting it in its own list, for example:
```json
[["custom 1", "custom 2"],["custom 3"],["follow"]]
```
If you are not using custom requirements, this is not necessary, as all criteria are required by default anyway.   

----------
Your first (required) advancement also needs to have a function reward:
### Function setup
The function reward of the first advancement needs the following added to it:  
```
advancement revoke only example:second
advancement grant only example:second follow 
```
where you replace `example:second` with your advancement id, and `follow` is the name of your criteria created above
If it doesn't use a function unique to itself, you can create one that is specifically designated to it, and then call the original function in it
## Example download
You can download an example of this <a href="/post_assets/force_advancement_order/downloads/example.zip" download="Advancement_order_example">here</a>.  
This is in the public domain under the unlicense <http://unlicense.org/>.