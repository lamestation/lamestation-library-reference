---
layout: functionpage
title: "gfx.Start"
library: "LameGFX"
type: function
syntax: "gfx.Start"
brief: "Initialize the LameGFX library."
return: The address of the drawing buffer.
---

Call `gfx.Start` to start LameGFX. It should only be started 
once at the beginning of your program, before all drawing 
operations, and should be connected to LameLCD right away.

```
lcd.Start(gfx.Start)
```

