---
layout: ref_function
title: "gfx.SetClipRectangle"
library: "LameGFX"
type: function
syntax: "gfx.SetClipRectangle(x1, y1, x2, y2)"
brief: Change the portion of the screen that will be drawn to by LameGFX.
param:
    x1: Left edge of the clip rectangle.
    y1: Top edge of the clip rectangle.
    x2: Right edge of the clip rectangle.
    y2: Bottom edge of the clip rectangle.
---

Call `gfx.SetClipRectangle` to set the clipping region, which 
is a rectangle from (0,0) to (128,64) by default. It will remain that size 
until you reset it to its normal size.

