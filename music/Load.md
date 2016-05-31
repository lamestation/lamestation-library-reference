---
layout: ref/function
title: "music.Load"
library: "LameMusic"
type: function
syntax: "music.Load(songAddr)"
brief: "Load a song to play."
param:
    songAddr: "<code>Addr</code> of the song object to play."
---

To load a song, call `music.Load` using the `Addr` function of 
the song object as an argument. Only one song can play at 
a time. Loading a new song will stop any currently playing one.

```
music.Load(mycoolsong.Addr)
```

