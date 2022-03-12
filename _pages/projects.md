---
layout: archive
title: "Projects"
permalink: /projects/
author_profile: true
---

{% include base_path %}

## 1. Multi-label Classification using 12-lead Electrocardiography (ECG) [link](https://github.com/juhha/12leadECG-ptbxl)
Given a large ECG dataset ([PTB-XL](https://physionet.org/content/ptb-xl/1.0.1/)), which contains 21,837 clinical 12-lead ECGs from 18,885 patients of 10 seconds, I performed 1D/2D classification using CNN ([XceptionNet](https://arxiv.org/pdf/1610.02357.pdf)). For 1D classification, the raw 1D heart signal was used. For 2D classification, different types of transformations were used: 2D [spectrogram](https://en.wikipedia.org/wiki/Spectrogram) (Short-Time Fourier Transform, STFT) and [scalogram](https://en.wikipedia.org/wiki/Continuous_wavelet_transform) (Continous Wavelet Transform, CWT). The difference of the raw/ transformed signals are shown below. I obtained the better classification performance (in respect to AUC score) in order of scalogram, spectrogram, and raw signal (from higher to lower), but the model time and space complexity were in order of raw signal, spectrogram, and scalogram (from lighter to more expansive).

1. Raw 1D signal
![example_image-ptb-sig](/images/projects/project_ptb_xl-1d_signal.png)
2. 2D spectrogram
![example_image-ptb-stft](/images/projects/project_ptb_xl-2d_stft.png)
3. 2D scalogram
![example_image-ptb-cwt](/images/projects/project_ptb_xl-2d_cwt.png)

## 2. UNet and BESNet for semantic segmentation [link](https://github.com/juhha/UNet-and-BESNet)
Reproduced 2 papers ([UNet](https://arxiv.org/abs/1505.04597) and [BESNet](https://link.springer.com/chapter/10.1007%2F978-3-030-00934-2_26)) for image segmentation. To test the performance, I used 2 public datasets ([The Oxford-IIIT Pet Dataset](https://www.robots.ox.ac.uk/~vgg/data/pets/) and [LGG Brain Segmentation Dataset](https://www.kaggle.com/mateuszbuda/lgg-mri-segmentation)). The result showed that BESNet performed better than UNet for image segmentation task, which proves the suggestion of the paper about the advantage of adding additional boundary prediction connection and special loss function (boundary-enhanced cross entropy). The training progress of BESNet in 1 validation data instance for each dataset is shown below.
![example_image-besnet-pet](/images/projects/project_besnet-pet@besnet_with_bece-shiba_inu_100.gif)
![example_image-besnet-brain](/images/projects/project_besnet-mri@besnet_with_bece-TCGA_CS_4944_20010208_8.gif)
