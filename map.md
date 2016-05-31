---
layout: ref/library 
title: "LameMap"
alias: map
brief: "A tile engine for LameGFX. It provides functions to display and interact with tile-based game maps."
folder: /demos/maps/
image: ParallaxScrolling.png
icon: map-o
---

Game maps consist of three parts: a tile map, a level map, and an optional collision map.

-   A *tile map* is a 2D array of sprites intended for creating maps, organized so that 
    they can be indexed by a level map. On LameStation, the tile map format is just an 
    ordinary sprite with frames.

    ![](islandfun_tiles.png)

-   A *collision map* mirrors the tile map and determines which tiles can be walked on 
    and which ones can't. On LameStation, a collision map is an image of black and white 
    squares, the same size as the tile map. A black square cannot be walked on, and a 
    white one can.

    ![](islandfun_collision.png)

-   A *level map* combines the data in the tile map and collision map to build a space 
    that can be navigated as part of the gameplay. The level map format is described in 
    the next section.

    ![](islandfun_demo.png)

### Level Map Format

#### Level Map Data

Map data is raw data describing what an area looks like and how the player can interact with it.

-   *width*, *height* (`0-65535`) - The width and height of the image in tiles.
-   *tile* - The array of tiles that make up this level, placed left-to-right, top-to-bottom.

```
DAT
map_data

word    <width>, <height>

byte    <tile>, [<tile>]...
```

Each tile in a map is one byte, with 1 bit used for collision, and the other 7 used for the tile number. Collision data is stored in the level to save space and so collision can be customized for the map.

![](tilebyte.png)

Tile 0 is used as a _null_ tile, so the maximum usable tilemap size is 127 tiles.

The collision bit stores whether a tile will register a collision when touched. All collision functions return 0 unless this bit is set.

#### Level Map Interface

The address of the map data can be passed directly to `map.Load`, unless stored in another object. If so, the following function is used as an interface.

```
PUB Addr
    return @map_data
```
