[![DOI](https://zenodo.org/badge/39132186.svg)](https://zenodo.org/badge/latestdoi/39132186) [![License: CC BY-NC-SA 4.0](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-ff69b4.svg)](http://creativecommons.org/licenses/by-nc-sa/4.0/) [![Build Status](https://travis-ci.org/MTG/otmm_makam_recognition_dataset.svg?branch=master)](https://travis-ci.org/MTG/otmm_makam_recognition_dataset)

# Hindustani Raga Phrase Dataset 

This repository hosts the dataset designed to test melodic phrase shape characterization methodologies on Hindustani raga music. It is composed of 12 recordings from ragas Deshkar and Bhupali in [CompMusic Project](http://compmusic.upf.edu/)'s [Dunya](http://dunya.compmusic.upf.edu/) Hindustani Music collection.

Please cite the publication below, if you use this dataset in your work:

> Ganguli, K.~K. (2019).  [MORTY: A Toolbox for Mode Recognition and Tonic Identification](http://mtg.upf.edu/node/3538). PhD thesis, Indian Institute of Technology Bombay, Mumbai, India.

The recordings are selected from commercial recordings carefully such that they cover diverse musical forms, vocal/instrumentation settings, and recording qualities (e.g. historical vs contemporary). Each recording in the dataset is identified by a 16-character long unique identifier called MBID, hosted in [MusicBrainz](http://musicbrainz.org). The makam and the tonic of each recording are annotated in the file [annotations.json](https://github.com/MTG/otmm_makam_recognition_dataset/blob/master/annotations.json).

The audio-related data in the test dataset is organized by each makam in the folder [data](https://github.com/MTG/otmm_makam_recognition_dataset/blob/master/data). Due to copyright reasons, we are unable to distribute the audio. Instead, we provide the predominant melody of each recording, computed by a state-of-the-art [predominant melody extraction algorithm](https://github.com/sertansenturk/predominantmelodymakam/commit/f8b7302bc657f90e2b10a0ffd988902935adc3d6) optimized for OTMM culture. These features are saved as text files (with the paths `data/[makam]/[mbid].pitch`) of a single column that contains the frequency values. The timestamps are removed to reduce the filesizes. The step size of the pitch track is 0.0029 seconds (an analysis window of 128 samples hop size of an mp3 with 44100 Hz sample rate), with which one can recompute the timestamps of samples. 

Moreover, the metadata of each recording is available in the repository, crawled from MusicBrainz using an [open source tool developed by us](https://github.com/sertansenturk/makammusicbrainz). The metadata files are saved as `data/[makam]/[mbid].json`.

For reproducibility purposes, we note the version of all tools we have used to generate this dataset in the file [algorithms.json](https://github.com/MTG/otmm_makam_recognition_dataset/blob/master/algorithms.json).

A complementary toolbox for this dataset is [MORTY](https://github.com/altugkarakurt/morty), which is a mode recognition and tonic identification toolbox. It can be used and optimized for any modal music culture. Further details are explained in the publication above. 

For more information, please contact the authors.

Erratum
------------
In November 2016, we discovered several errors in the tonic annotations. We are currently verifying the annotations. See the description in [otmm_tonic_dataset](https://github.com/MTG/otmm_tonic_dataset#erratum) for more details and up-to-date progress.

<a name="License"></a>License
--------------------
<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/">Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License</a>.
