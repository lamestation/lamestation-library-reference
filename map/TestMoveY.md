---
layout: ref/function
title: "map.TestMoveY"
library: "LameMap"
type: function
syntax: "map.TestMoveY(x, y, w, h, newy)"
brief: "Apply vertical movement to an object's position and test if it will collide."
param:
    x: Horizontal position of the rectangle.
    y: Vertical position of the rectangle.
    w: Width of the rectangle.
    h: Height of the rectangle.
    newy: New vertical position of the rectangle.
return: |
    A +/- integer offset that when added to `newy` will remove
    the object under test from collision. A zero value
    indicates no collision has occurred.
---

Knowing whether a collision has happened is often not enough, 
as you might need to keep the player inside a known region. 
`map.TestMoveX` and `map.TestMoveY` allow you to test if a 
potential horizontal or vertical movement will cause a 
collision.

If so, it will return a correction factor needed to remove 
the object from the collision. In this way, you can build 
walls that players can slide along and won't escape from.

{% include info %}
Only valid map regions are tested for collisions; positions that are off the map area will always return 0.
{% include infoend %}

{% include info %}
The `TestMove-` functions only check for collisions once at the new location. If the distance is large enough, they may miss potential collisions (e.g. halfway
between the old and new locations).
{% include infoend %}
