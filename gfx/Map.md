---
layout: ref_function
title: "gfx.Map"
library: "LameGFX"
type: function
syntax: "gfx.Map(tilemap, levelmap, offset_x, offset_y, x1, y1, x2, y2)"
brief: "Draw a tile-based level map."
param:
    tilemap: The address of the tile map graphics data.
    levelmap: The address of the level map data. 
    offset_x: The horizontal position of the map viewport relative to the origin. 
    offset_y: The vertical position of the map viewport relative to the origin. 
    x1: The left edge of the map viewport on the screen.
    y1: The top edge of the map viewport on the screen.
    x2: The right edge of the map viewport on the screen.
    y2: The bottom edge of the map viewport on the screen.
---

Use `gfx.Map` to draw level maps directly, or you can use LameMap 
for more functionality.
