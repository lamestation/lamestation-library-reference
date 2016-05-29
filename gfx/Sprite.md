---
layout: ref_function
title: "gfx.Sprite"
library: "LameGFX"
type: function
syntax: "gfx.Sprite(source, x, y, frame)"
brief: "Draw an image of any size to the screen."
param:
    source: The address of the sprite graphics.
    x: Horizontal position of sprite.
    y: Vertical position of sprite.
    frame: Frame of sprite to draw.
---

Call `gfx.Sprite` to draw images to the screen. All built-in drawing
functions are built on `gfx.Sprite` except for [gfx.Blit](../Blit/).

If an image is exactly 128x64 pixels, use `gfx.Blit` for much faster drawing.
