---
layout: ref/function
title: "fn.TestBoxCollision"
library: "LameFunctions"
type: function
syntax: "fn.TestBoxCollision(x1, y1, w1, h1, x2, y2, w2, h2)"
brief: "Test if two rectangular regions of the screen overlap."
param:
    x1, y1, w1, h1: The dimensions of the first object.
    x2, y2, w2, h2: The dimensions of the second object.
---

Test if two rectangles on the screen overlap. If you want two objects the screen to 
interact with each other, you might need this.

For a working example, try `demos/collision/TestBoxCollision.spin` in the LameStation SDK.
