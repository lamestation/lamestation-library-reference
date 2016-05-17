---
layout: librarypage 
title: "LameGFX"
alias: gfx
brief: "The LameStation graphics engine, providing a drawing surface and basic drawing functions."
folder: /demos/graphics/
constant:
    SCREEN_W: Width of the screen in pixels.
    SCREEN_H: Height of the screen in pixels.
    QUARTERSPEED: Frame 
image: blit.png
---

Call `gfx.Start` to start LameGFX. It should only be started once at the beginning of your program, before all drawing operations, and should be connected to LameLCD right away.

```
lcd.Start(gfx.Start)
```

Clear the screen to black with `gfx.Clear`, or fill to any color with `gfx.Fill`.

Call `gfx.Sprite` to draw images to the screen. If an image is exactly 128x64 pixels, use `gfx.Blit` for much faster drawing.

Use `gfx.Map` to draw level maps directly, or you can use LameMap for more functionality.

`gfx.InvertColor` changes all black pixels to white, and vice versa. This is useful as a cool effect or reusing graphics.

### Clipping

LameGFX supports clipping, which allows you to limit the part of the screen that functions will draw to. This is useful if, for example, you want to show half of an image, or a progress bar that can fill up.

Call `gfx.SetClipRectangle` to set the clipping region, which is a rectangle from (0,0) to (128,64) by default. It will remain that size until you reset it to its normal size.

The first point is inclusive, while the second is exclusive. That means that a region of (0, 0, 128, 64) allows you to draw on pixels from (0,0) to (127,63).

{% include info %}
The second point must be to the right and down relative to the first, otherwise the clip rectangle will be of size (0,0), or not drawable.
{% include infoend %}

### Direct Drawing

You can draw to the LameGFX buffer directly. First, you must enable access. This is done by grabbing its address during setup.

```
VAR
    word    buffer
PUB
    lcd.Start(buffer := gfx.Start)
```

You can now access the 2048-byte block of memory pointed to by `buffer`.

LameGFX will wait until the previous drawing command is finished before starting a new one. However, advanced users may want to create their own drawing functions. If so, use `gfx.WaitToDraw` to ensure your function plays well with LameGFX.

### Sprite Format

LameGFX has its own format for sprites.

#### Sprite Data

Each sprite has the same structure.

- *frameboost* - The size of a frame in bytes, or `width * height / 4`.
- *width*, *height* (`0-65535`) - The width and height of each frame in pixels.
- *data...* - Image data.

```
DAT
gfx_data

word    <frameboost>
word    <width>, <height>

word    <data>, [<data>]...
```

Each pixel is two bits, so there are 8 pixels per word. Image data should be organized left-to-right, top-to-bottom, with `frameboost / 2` words for each frame.

LameGFX supports 3 visible colors and one transparent color that is never drawn.

- **Black** - 0
- **White** - 1
- **Transparent** - 2
- **Gray** - 3

Sprites can contain multiple images, or frames, so that they can be animated by your program. The first frame is frame 0.

#### Sprite Interface

The address of image data can be passed directly to `gfx.Sprite` and `gfx.Blit`, unless stored in another object. If so, use this interface:

```
PUB Addr
    return @gfx_data
```

### Creating Sprite Objects

LSImage or the command-line `img2dat` can be used to convert images into sprite objects, or they can be written by hand.
