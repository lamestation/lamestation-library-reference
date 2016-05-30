---
layout: ref/function
title: "map.DrawRectangle"
library: "LameMap"
type: function
syntax: "map.DrawRectangle(offset_x, offset_y, x1, y1, x2, y2)"
brief: "Draw the current map to a portion of the screen."
param:
    offset_x: The horizontal offset from the map origin.
    offset_y: The vertical offset from the map origin.
    x1: The left edge of the viewing window.
    y1: The top edge of the viewing window.
    x2: The right edge of the viewing window (exclusive).
    y2: The bottom edge of the viewing window (exclusive).
---

The bottom and right coordinates are **exclusive**, which means
they specify a rectangle up to, but not including their points.
