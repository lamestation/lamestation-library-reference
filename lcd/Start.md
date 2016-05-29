---
layout: ref/function
title: "lcd.Start"
library: "LameLCD"
type: function
syntax: "lcd.Start(buffer)"
brief: "Initialize the LameLCD library."
param:
    buffer: The address of the drawing buffer (word).
return: The address of the LCD buffer.
---

Call `lcd.Start` once at the beginning of your program 
to use LameLCD, giving the drawing surface returned when 
LameGFX is started as the argument. Due to this, its 
recommended to start LameLCD and LameGFX at the same time, 
like so:

```
lcd.Start(gfx.Start)
```

The screen will not update with this command.
