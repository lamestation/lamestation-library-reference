---
layout: ref/function
title: "audio.SetParam"
library: "LameAudio"
type: function
syntax: "audio.SetParam(channel, type, value)"
brief: Manually set a parameter of the audio channel.
param:
    channel: "The oscillator channel (0-3)"
    type:    _ATK, _DEC, _SUS, _REL, _WAV, _CONTROL
    value:   Byte-sized value dependent on parameter (0-255).
---
