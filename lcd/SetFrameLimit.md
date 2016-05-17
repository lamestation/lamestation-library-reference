---
layout: functionpage
title: "lcd.SetFrameLimit"
library: "LameLCD"
type: function
syntax: "lcd.SetFrameLimit(frequency)"
brief: "Set an upper limit to the screen refresh rate."
param:
    frequency: "The desired upper limit. This will be rounded down to 70Hz, 35Hz, or 17Hz."
---

Enable `lcd.SetFrameLimit` to have LameLCD automatically limit 
the frame limit to one of three speeds.

- [QUARTERSPEED](../QUARTERSPEED/)
- [HALFSPEED](../HALFSPEED/)
- [FULLSPEED](../FULLSPEED/)

Frame rate limiting is disabled by default.

