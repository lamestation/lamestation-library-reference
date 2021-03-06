---
layout: ref/library 
title: "LameMusic"
alias: music
brief: "A sequencer for LameAudio that allows your games to play music."
folder: /demos/music/
image: jukebox.png
icon: music 
---

Call `music.Start` once at the beginning of your program to start the music engine.

{% include info %}
LameAudio must be started before LameMusic.
{% include infoend %}

To load a song, call `music.Load` using the `Addr` function of the song object as an argument.  Only one song can play at a time. Loading a new song will stop any currently playing one.

```
music.Load(mycoolsong.Addr)
```

You can use the `music.Play` command to play a song once, or `music.Loop` to play it forever. Call `music.IsPlaying` to find out if a song is currently playing.

Once you're tired of listening to music, call `music.Stop` to end the song. Playing the song again will start over from the beginning.

### Song Format

{% include info %}
Software to create LameMusic song objects is planned; for now, songs must be created by hand.
{% include infoend %}

LameStation songs consist of two main sections: pattern and sequence data.

#### Pattern Data

Patterns contain melodies, riffs, harmonies and any musical parts that fit in a measure.

- *Notes per measure* (first byte) (`0-255`) - Each pattern must have exactly this many notes.
- *Note* (`0-127`) - Play note n between 0 and 127.
- *Stop note* (`$83`) - Stop playing note.
- *Do nothing* (`$82`) - Do nothing (continue playing or not playing current note).

```
DAT

pattern_data
byte    4

byte    42,  44,  46,  49
byte    42, $82, $82, $83
```

#### Sequence Data

The sequence defines how the patterns are arranged in time and across channels. There should be one command, as many times as you want.

- *Pattern* (`<ch1>`, `<ch2>`, `<ch3>`, `<ch4>`) - Set next pattern to pattern 1-127 for all four channels. Pattern 0 plays nothing.
- *End song* (`$80`) - End the song.
- *ADSRW* (`$A0`, `<a>`, `<d>`, `<s>`, `<r>`, `<w>`) - Change the sound of channel(s).
- *Tempo* (`$B0`, `0-255`) - Change the tempo of the song.
- *Transpose* (`$C0`, `-128-127`) - Transpose the channel up or down number of notes.

```
DAT

sequence_data
byte    1, 0, 0, 0
byte    $80
```

#### Song Interface

For LameMusic to access the song object, some extra code is needed. This code provides an address which LameMusic reads to figure out where the song data is.

```
DAT
    song_data
    word    @pattern_data, @sequence_data
PUB Addr
    result.word[1] := @@0
    result.word{0} := @song_data
```
