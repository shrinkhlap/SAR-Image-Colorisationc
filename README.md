# SAR-to-Optical Image Colorization using Robust U-Net

## Overview

This project implements a **deep learning model** to colorize grayscale **Sentinel-1 SAR images** into realistic **Sentinel-2 optical images**. The model is based on a **Robust U-Net architecture** that handles minor spatial misalignments between SAR and optical images, enabling high-quality image-to-image translation.

## Features

* Converts **grayscale SAR images** to **RGB optical images**.
* **Automatic spatial alignment** in the decoder for robustness.
* Trained on paired Sentinel-1 and Sentinel-2 satellite images.
* Demonstrates low reconstruction loss and accurate colorization.

## Model Architecture

* **Encoder:** Captures multi-scale features from input SAR images.
* **Bottleneck:** Extracts high-level representations.
* **Decoder:** Upsamples and aligns features to generate colorized output.
* **Skip Connections:** Preserve spatial details from encoder to decoder.


### Example Output

* Input: Grayscale Sentinel-1 image
* Output: Colorized Sentinel-2 style image

## Training

* Trained with **MSE loss** on paired Sentinel-1 and Sentinel-2 images.
* Achieved progressively decreasing loss (\~0.039 → 0.033 over 5 epochs).
* Optimized for robust generalization across different terrains.

## References

* U-Net: [Ronneberger et al., 2015](https://arxiv.org/abs/1505.04597)
* Sentinel-1 and Sentinel-2 datasets from [Copernicus Open Access Hub](https://scihub.copernicus.eu/)

## License

MIT License – feel free to use and modify for research or educational purposes.


