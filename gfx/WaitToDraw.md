---
layout: functionpage
title: "gfx.WaitToDraw"
library: "LameGFX"
type: function
syntax: "gfx.WaitToDraw"
brief: "Wait until the last drawing operation has completed before continuing."
---

LameGFX will wait until the previous drawing command is finished before starting 
a new one. However, advanced users may want to create their own drawing functions. 

If so, use `gfx.WaitToDraw` to ensure your function plays well with LameGFX.

