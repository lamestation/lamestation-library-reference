---
layout: ref/function
title: "audio.SetEnvelope"
library: "LameAudio"
type: function
syntax: "audio.SetEnvelope(channel, enabled)"
brief: Toggle the ADSR envelope generator on the given audio channel.
param:
    channel:    "The oscillator channel (0-3)"
    enabled:     True enables the envelope; false disables it.
---

The envelope can be toggled with `audio.SetEnvelope`.

- If enabled, you can play and stop notes with the `audio.PlaySound` and `audio.StopSound` commands.

- If disabled, you can control channel volume manually using `audio.SetVolume`, which is useful for creating sound effects. You can also manually start and stop the envelope with `audio.StartEnvelope` and `audio.StopEnvelope`.
