---
layout: functionpage
title: "gfx.Sprite"
library: "LameGFX"
type: function
syntax: "gfx.Sprite(source, x, y, frame)"
brief: "Draw a screen-sized image to (0,0)."
param:
    source: The address of the sprite graphics.
    x: Horizontal position of sprite.
    y: Vertical position of sprite.
    frame: Frame of sprite to draw.
---

This function is the only built-in function that doesn't use
`gfx.Sprite` for drawing. It performs a single block copy of the image,
which is much faster than sprite drawing. 
