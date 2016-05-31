---
layout: ref/function
title: "audio.LoadPatch"
library: "LameAudio"
type: function
syntax: "audio.LoadPatch(patchAddr)"
brief: Load a new patch.
param:
    address:    The address of the new patch to load.
---

You can change all parameters at once with the `audio.LoadPatch` command. This is useful if you change instruments often.

A patch is formatted as follows:

```
byte    <attack>, <decay>, <sustain>, <release>, <waveform>
```
