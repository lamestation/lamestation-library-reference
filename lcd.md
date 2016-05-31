---
layout: ref/library 
library: "Library Reference"
title: "LameLCD"
alias: lcd
brief: "A 128x64 pixel, three-color display driver for the LameStation."
folder: /demos/graphics/
icon: picture-o
---

Call `lcd.Start` once at the beginning of your program to use LameLCD, giving the drawing surface returned when LameGFX is started as the argument. Due to this, its recommended to start LameLCD and LameGFX at the same time, like so:

```
lcd.Start(gfx.Start)
```

The screen will not update on its own. Call `lcd.Draw` to send the graphics buffer to the screen.

All colors on the screen can be inverted with the `lcd.InvertScreen` command, which is a nice visual effect.

`lcd.Draw` can be called at any time to copy the drawing buffer to the display buffer. This is likely to happen when LameLCD is already updating the physical screen, which will cause the screen to flicker.

To prevent flickering, call `lcd.WaitForVerticalSync` before calling `lcd.Draw` to ensure LameLCD is not busy when `lcd.Draw` is called. Enable `lcd.SetFrameLimit` to have LameLCD do this automatically, at one of three speeds. Frame rate limiting is disabled by default.

### Direct Access

LameLCD is usually started with LameGFX. However, it can also be started with a custom buffer if the size and alignment match (2048 bytes, long-aligned).
