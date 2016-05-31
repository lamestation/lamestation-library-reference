---
layout: ref/function
title: "txt.Load"
library: "LameText"
type: function
syntax: "txt.Load(source, start, w, h)"
brief: "Load a font into LameText."
param:
    source: The address of the font sprite.
    start:  The first character in the sprite (usually " ").
    w, h:   Desired letter spacing. 
---

Begin by loading a font into LameText with `txt.Load`, passing 
the font address, first character, and character width and 
height. Only one font can be loaded at a time, but fonts can 
be switched at any time. 

Changing the width and height of the font changes the spacing 
of letters. Setting to 0,0 will use the sprite frame size for
spacing.
