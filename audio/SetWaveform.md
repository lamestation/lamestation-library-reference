---
layout: ref/function
title: "audio.SetWaveform"
library: "LameAudio"
type: function
syntax: "audio.SetWaveform(channel, value)"
brief: Set the waveform of the given audio channel.
param:
    channel:    The oscillator channel (0-3).
    waveform:   Index of waveform to use.
---

You can load one of the following waveforms.

| Value   | Name     | Waveform            |
|---------|----------|---------------------|
| 0       | Square   | ![](0_square.png)   |
| 1       | Sawtooth | ![](1_saw.png)      |
| 2       | Triangle | ![](2_triangle.png) |
| 3       | Sine     | ![](3_sine.png)     |
| 4       | Noise    | ![](4_noise.png)    |
| 5       | Sample   | ![](5_sample.png)   |
{: class="table"}

The _Sample_ waveform is a 512B block of audio data, enough for one cycle. Call `audio.SetSample` with the address of a sample to load it. Only one sample can be used at a time.

A collection of ready-made samples can be found in the `/media/samples/` folder of the SDK.

