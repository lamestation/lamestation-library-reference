---
layout: ref/library 
title: "LameText"
alias: txt
brief: "Text-drawing functionality for LameStation games."
folder: /demos/text/
icon: font
---

LameGFX must be started before LameText can be used.

Begin by loading a font into LameText with `txt.Load`, passing
the font address, first character, and character width and 
height. Only one font can be loaded at a time, but fonts can 
be switched at any time. Changing the width and height of the 
font changes the spacing of letters.

Now you can use any of the text-drawing commands, keeping in mind that they won't be visible until `lcd.Draw` is called.

### Font Format

LameStation fonts are regular LameGFX sprites, but organized according to the [ASCII table](http://www.asciitable.com/).

![](font6x8_normal.png)

You can find a collection of ready-to-use fonts in `/media/fonts/`.
