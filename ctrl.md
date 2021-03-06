---
layout: ref/library 
title: "LameControl"
alias: ctrl
brief: "Use the LameStation's joystick and buttons."
icon: gamepad
---

- `ctrl.Start` - Start the LameControl library.
- `ctrl.Update` - Update the state of all controls.
- `ctrl.WaitKey` - Wait until `A` or `B` button is pressed.

*Button Commands*

- `ctrl.A` - Returns true if the 'A' button is pressed.
- `ctrl.B` - Returns true if the 'B' button is pressed.

*Joystick Commands*

- `ctrl.Up` - Returns true if the joystick is tilted up.
- `ctrl.Right` - Return whether the joystick is tilted right.
- `ctrl.Down` - Return whether the joystick is tilted down.
- `ctrl.Left` - Return whether the joystick is tilted left.

== About

The LameStation has six hardware controls for user input.

![](control_layout.png)

Before you can use them, you must call `ctrl.Start` once at the beginning of your program. This tells the Propeller to listen to the controls.

To read the current state of the controls, call `ctrl.Update`. A good place to do this is at the beginning of your main game loop, but it can be called at any time. If this is never called, all other commands will always return false.

```
PUB Main
    repeat
        ctrl.Update
```

After calling `ctrl.Update`, you can call any of the button or joystick commands to get their state. The values returned will not update until `ctrl.Update` is called again.

```
if ctrl.Up
    ' jump really high
if ctrl.A or ctrl.B
    ' do something
```
