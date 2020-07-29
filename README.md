# Speaker Diarization

This project uses two modules to carry out speaker diarization. Speaker embeddings are created from [VGG-Speaker-Recognition](https://github.com/WeidiXie/VGG-Speaker-Recognition) and the diarization is performed using Google's proposed implementation of [UIS-RNN](https://github.com/google/uis-rnn).

This repository is a [fork](https://github.com/taylorlu/Speaker-Diarization) and the orignal documentation can be found in ORIGINAL.md, which details how the models were trained.

## Dependencies

1. Python 3.5+
2. Pytorch 1.3.0+ (used by UIS-RNN)
3. Tensorflow 1.8.0+ (used by VGG-speaker-recognition, originally on v1.8.0)
4. keras 2.2.4+
5. numpy 1.15.1+
6. numba 0.48.0
7. librosa
8. pyaudio

The easiest way to install the required libraries without version conflicts is to use Anaconda.

_Note: If TF 2.0+ is installed, be sure to change the imports in `ghostvlad/toolkits.py` and `ghostvlad/model.py` to the compat version_

## Running diarization

On the command line, run

```bash
python speakerDiarization.py --input <path-to-audio-file>
```

and the results will be printed to the command line.  
Optionally, to send the output to a file, add `--output <path-to-write>`.

The result on the commandline/in the file will be similar to (from an audio clip with 3 speakers):

```bash
========= 0 =========
0:00.288 ==> 0:04.406
0:07.699 ==> 0:16.461
0:33.921 ==> 0:35.8
========= 1 =========
0:04.406 ==> 0:07.699
0:16.461 ==> 0:19.594
0:30.371 ==> 0:33.921
0:41.19 ==> 0:44.185
========= 2 =========
0:19.594 ==> 0:30.371
0:35.8 ==> 0:41.19
```
