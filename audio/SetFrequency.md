---
layout: ref/function
title: "audio.SetFrequency"
library: "LameAudio"
type: function
syntax: "audio.SetFrequency(channel, value)"
brief: Set the frequency increment of the given audio channel.
param:
    channel:    The oscillator channel (0-3).
    value:      The new frequency increment to set (long).
---

This function controls the phase accumulator directly, allowing
you to generate frequency possible with the synthesizer.
