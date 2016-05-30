---
layout: ref/library 
title: "LameMap"
alias: map
brief: "A tile engine for LameGFX. It provides functions to display and interact with tile-based game maps."
folder: /demos/maps/
image: ParallaxScrolling.png
---

=== Commands

- `map.TestCollision` - Test if the region has collided with a map tile.
- `map.TestMoveX` - Apply horizontal movement to an object's position and test if it will collide.
- `map.TestMoveY` - Apply vertical movement to an object's position and test if it will collide.

=== Constants

- `TILEMASK`, `COLLIDEMASK` - Bitmasks for accessing tile and collision data in level maps.

=== About

There are two ways to draw a map to the screen: `map.Draw` draws the map to the whole screen, while `map.DrawRectangle` limits the map to a region with the corners (x1, y1) and (x2, y2). Both use an `offset_x` and `offset_y` that determine which portion of the map to show.

image::drawmap.png[title='The red rectangle is the offset, while the blue rectangle is the size of the visible map portion.']

You can get the number of horizontal and vertical tiles in your map with `map.Width` and `map.Height`.

```
mapsize := map.Width * map.Height
```

LameMap has collision support built in. `map.TestPoint` returns if a tile has collision enabled. You can test whether or not collision has occurred with `map.TestCollision`, passing the rectangle of the object.

{% include info %}
Only valid map regions are tested for collisions; positions that are off the map area will always return 0.
{% include infoend %}

Knowing whether a collision has happened is often not enough, as you might need to keep the playing inside a known region. `map.TestMoveX` and `map.TestMoveY` allow you to test if a potential horizontal or vertical movement will cause a collision. If so, it will return a correction factor needed to remove the object from the collision. In this way, you can build walls that players can slide along and won't escape from.

[IMPORTANT]
The `TestMove-` functions only check for collisions once at the new location. If the distance is large enough, they may miss potential collisions (e.g. halfway
between the old and new locations).

=== Map Components

Game maps consist of three parts: a tile map, a level map, and an optional collision map.

- A *tile map* is a 2D array of sprites intended for creating maps, organized so that they can be indexed by a level map. On LameStation, the tile map format is just an ordinary sprite with frames.
+
image:islandfun_tiles.png[]
- A *collision map* mirrors the tile map and determines which tiles can be walked on and which ones can't. On LameStation, a collision map is an image of black and white squares, the same size as the tile map. A black square cannot be walked on, and a white one can.
+
image:islandfun_collision.png[]
- A *level map* combines the data in the tile map and collision map to build a space that can be navigated as part of the gameplay. The level map format is described in the next section.
+
image:islandfun_demo.png[]

=== Level Map Format

==== Level Map Data

Map data is raw data describing what an area looks like and how the player can interact with it.

- *width*, *height* (`0-65535`) - The width and height of the image in tiles.
- *tile* - The array of tiles that make up this level, placed left-to-right, top-to-bottom.

[source]
----
DAT
map_data

word    <width>, <height>

byte    <tile>, [<tile>]...
----

Each tile in a map is one byte, with 1 bit used for collision, and the other 7 used for the tile number. Collision data is stored in the level to save space and so collision can be customized for the map.

image:tilebyte.png[]

Tile 0 is used as a _null_ tile, so the maximum usable tilemap size is 126 tiles.

The collision bit stores whether a tile will register a collision when touched. All collision functions return 0 unless this bit is set.

==== Level Map Interface

The address of the map data can be passed directly to `map.Load`, unless stored in another object. If so, the following function is used as an interface.

[source]
----
PUB Addr
    return @map_data
----