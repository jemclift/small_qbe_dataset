# small_qbe_dataset 🎶

### Introduction

This is a dataset aimed at helping test query-by-example music recognition. It is a small data set, based on only 30 songs from the GTZAN dataset as it is time consuming to produce recodings.

Primarily two test scenarios have been considered, concerning 2 different types of distortion:

| Testing **Noise Resistance** | Testing **Pitch & Tempo Resistance** |
| --- | --- |
| Each of the standard set of samples were recorded in three different environments: **quiet**, **cafe**, and **street**. | Each of the standard set of samples were distorted three different ways: **pitch only**, **tempo only**, and **pitch and tempo**. |



### Usage

#### Songs

- `/full songs/songs/` contains 30 songs comprising a random sample of 3 tracks from each of the 10 GTZAN genres.

- `full songs/songs_tempo_altered` contains the same 30 songs tempo adjusted by a multiplier ranging from 0.5x to 2.0x. The multiplier has been appended to the filename after the flag `_t`.

#### Samples

- `/samples/unchanged/` contains 1 10s sample from each of the 30 songs with a random offset. The offset has been appended to the filename after the flag `_o`. For files not tempo distored, the offset will be somewhere between 0 and 20.

- `/samples/pitch_altered/` contains pitched versions of the `unchanged` samples. A random semitone pitch shift between -12 (one whole octave down) and 12 (one whole octave up) has been appended to the filename after the `_s` tag.

- `/samples/tempo_altered/` contains 1 10s sample of each of the `songs_tempo_altered` songs. The offset for each sample from the tempo altered source has been appended afte the flag `_o`.

- `/samples/pitch_and_tempo_altered/` contains pitch shifted version of the `/samples/tempo_altered/` samples. A random semitone pitch shift between -12 (one whole octave down) and 12 (one whole octave up) has been appended to the filename after the `_s` tag.

#### Recording

TODO

#### Other

For convenience of re-recording, combined versions of the samples have been provided. The idea being that if you want to re-record the samples, it is easier to record the whole thing, trim it and then clip into 10s chunks. For that purpose, text files with the filenames of the samples in the order they apear in the combined files have also been provided.