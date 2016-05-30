---
layout: ref/function
title: "map.TestCollision"
library: "LameMap"
type: function
syntax: "map.TestCollision(x, y, w, h)"
brief: "Test if the region has collided with a map tile."
param:
    x: Horizontal position of the rectangle.
    y: Vertical position of the rectangle.
    w: Width of the rectangle.
    h: Height of the rectangle.
return: True if collision occurred, otherwise false.
---

LameMap has collision support built in. You can test whether 
or not collision has occurred with `map.TestCollision`, passing the rectangle to test.

