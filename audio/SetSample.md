---
layout: ref/function
title: "audio.SetSample"
library: "LameAudio"
type: function
syntax: "audio.SetSample(address)"
brief: Load a new sample.
param:
    address:    The address of the new sample to load.
---

The _Sample_ waveform is a 512B block of audio data, enough for one cycle. Call `audio.SetSample` with the address of a sample to load it. Only one sample can be used at a time.

A collection of ready-made samples can be found in the `/media/samples/` folder of the SDK.
