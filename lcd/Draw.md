---
layout: ref_function
title: "lcd.Draw"
library: "LameLCD"
type: function
syntax: "lcd.Draw"
brief: "Send contents of the drawing buffer to the screen."
---

Even after starting the LCD driver, the screen will not update
until it is told to do so.

`lcd.Draw` can be called at any time to copy the drawing buffer
to the display buffer. This is likely to happen when LameLCD 
is already updating the physical screen, which will cause the 
screen to flicker.
