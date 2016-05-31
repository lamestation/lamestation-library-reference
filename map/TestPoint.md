---
layout: ref/function
title: "map.TestPoint"
library: "LameMap"
type: function
syntax: "map.TestPoint(x, y)"
brief: "Test whether a tile in the map is collidable."
param:
    x: The horizontal index of the tile.
    y: The vertical index of the tile.
return: True if collidable, otherwise false.
---

LameMap has collision support built in. `map.TestPoint` returns whether a tile has collision enabled. 
You can test whether or not collision has occurred with `map.TestCollision`, passing the rectangle of the object.

{% include info %}
Only valid map regions are tested for collisions; positions that are off the map area will always return 0.
{% include infoend %}
