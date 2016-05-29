---
layout: ref_function
title: "lcd.WaitForVerticalSync"
library: "LameLCD"
type: function
syntax: "lcd.WaitForVerticalSync"
brief: "Wait until the start of the next LCD frame before continuing."
---

To prevent flickering, call `lcd.WaitForVerticalSync` before calling `lcd.Draw`
 to ensure LameLCD is not busy when `lcd.Draw` is called. 

