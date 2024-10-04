PyTorch + Catalyst implementation of [Looking to Listen at a Cocktail Party](https://arxiv.org/abs/1804.03619).

This repository handles the training process. For inference, checkout the GUI wrapper: [SpeechSeparationUI](https://github.com/RajKhandor/SpeechSeparationUI) in PyQT.

This repository has been merged with [asteroid](https://github.com/mpariente/asteroid) as a [recipe](https://github.com/mpariente/asteroid/tree/master/egs/avspeech).

# Table of Contents
1. [Requirements](#requirements)
2. [References](#references)

# Requirements

1. **Computation**

    We ran this program on two GPUs, 1050 Mobile and Tesla V100. We did not conduct any benchmarks but, V100 was roughly 400x faster. It also depends on how much data you download. Hence, **any server grade GPU** should be feasible.

2. **Storage**

    This program does generate a lot of files (download and otherwise). Each audio file is 96kiB in size. For 7k unique audio clips and at a 70/30 train and validation split it occupied  ~120GiB of storage space. Hence, **1TB** minimum if you download more audio clips.
3. **Memory**

    **Minimum of 4GB VRAM** is required. It can handle a batch size of 2.
    At 20 batch size, on two GPUs, it occupied 16GiB VRAM on each GPU. 



### Example Prediction after 37 epochs (Suffering from overfitting)
![validation spectrogram](data/images/validation_example.png "Validation Spectrogram")

### Loss Plot
![loss plot](data/images/loss_plot.png "Loss Plot")

### SNR Plot
![snr plot](data/images/snr_plot.png "SNR Plot")

# References

1. Looking to Listen at a Cocktail Party: https://arxiv.org/abs/1804.03619
2. Discriminative Loss: https://arxiv.org/abs/1502.04149
3. PyTorch: pytorch.org
4. Catalyst: https://github.com/catalyst-team/catalyst
5. mir_eval: https://github.com/craffel/mir_eval
6. pysndfx: https://github.com/carlthome/python-audio-effects/tree/master/pysndfx
