---
layout: ref/function
title: "audio.SetADSR"
library: "LameAudio"
type: function
syntax: "audio.SetADSR(channel, attack, decay, sustain, release)"
brief: Set all parameters of the ADSR envelope shape.
param:
    channel:    "The oscillator channel (0-3)"
    attack:     Time from silence to full volume (0-127).
    decay:      Time from full volume to sustain (0-127).
    sustain:    The volume sustained while the note is held (0-127).
    release:    Time from note release to silence (0-127).
---

ADSR stands for *Attack, Decay, Sustain, and Release*.

![](adsr.png)

- *Attack* (`0-127`) - The time from silence to full volume.
- *Decay* (`0-127`) - The time from the max value to...
- *Sustain* (`0-127`) - The volume at which the note is held while pressed.
- *Release* (`0-127`) - The time from sustain to silence.

