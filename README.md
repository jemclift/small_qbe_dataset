# small_qbe_dataset 🎶

### Introduction

This is a dataset aimed at helping test query-by-example music recognition. It is a small data set, based on only 30 songs from the GTZAN dataset as it is time consuming to produce recodings. There are 210 different live recordings in various conditions and distortions.

Primarily two test scenarios have been considered, concerning 2 different types of distortion:

| Testing **Noise Resistance** | Testing **Pitch & Tempo Resistance** |
| --- | --- |
| Each of the standard set of samples were recorded in three different environments: **quiet**, **cafe**, and **street**. | Each of the standard set of samples were distorted four different ways: **pitch only**, **tempo only**, **pitch and tempo** and  **speed** (where both are changed in respect to each other). |
| Aim is to test different levels of background noise. | Aim is to recognise pitch and tempo altered samples. |


### Usage

#### Songs

- `/full_songs/songs/` contains 30 songs comprising a random sample of 3 tracks from each of the 10 GTZAN genres.

- `full_songs/songs_tempo_altered` contains the same 30 songs tempo adjusted by a multiplier ranging from 0.5x to 2.0x. The multiplier has been appended to the filename after the flag `_t`.

- `full_songs/songs_speed_altered` contains the same 30 songs with speed adjusted by a multiplier ranging from 0.5x to 2.0x. The multiplier has been appended to the filename after the flag `_x`

#### Samples

- `/samples/unchanged/` contains 1 10s sample from each of the 30 songs with a random offset. The offset has been appended to the filename after the flag `_o`. For files not tempo distored, the offset will be somewhere between 0 and 20.

- `/samples/pitch_altered/` contains pitched versions of the `unchanged` samples. A random semitone pitch shift between -12 (one whole octave down) and 12 (one whole octave up) has been appended to the filename after the `_s` tag.

- `/samples/tempo_altered/` contains 1 10s sample for each of the `songs_tempo_altered` songs. The offset for each sample from the tempo altered source has been appended after the flag `_o`.

- `/samples/pitch_and_tempo_altered/` contains pitch shifted version of the `/samples/tempo_altered/` samples. A random semitone pitch shift between -12 (one whole octave down) and 12 (one whole octave up) has been appended to the filename after the `_s` tag.

- `/samples/speed_altered/` contains 1 10s sample for each of the `songs_speed_altered` songs. The offset for each sample from the speed altered source has been appended after the flag `_o`.

#### Recordings

- `/recordings/*` contains folders with live recordings of their respective samples.

#### Other

For convenience of re-recording, combined versions of the samples have been provided. The idea being that if you want to re-record the samples, it is easier to record the whole thing, trim it and then clip into 10s chunks. For that purpose, text files with the filenames of the samples in the order they apear in the combined files have also been provided.