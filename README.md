
#  SAR-to-Optical Image Colorization using Robust U-Net

## Overview

This project implements a **deep learning pipeline** to colorize grayscale **Sentinel-1 SAR images** into realistic **Sentinel-2 optical images**. It uses a **Robust U-Net architecture** capable of handling small spatial misalignments between SAR and optical imagery, achieving high-quality image-to-image translation.

* Converts SAR grayscale images to RGB optical images.
* Maintains robustness to slight spatial mismatches.
* Trained on paired Sentinel-1 and Sentinel-2 satellite images.

---

## Features

* **Grayscale-to-Color Translation:** Transforms SAR images into optical RGB images.
* **Robust U-Net:** Automatically aligns features in the decoder for better reconstruction.
* **High-Quality Results:** Low reconstruction loss and accurate colorization.
* **Visualization:** Compare input SAR images and predicted optical outputs.

---

## Model Architecture

* **Encoder:** Captures multi-scale features from input SAR images.
* **Bottleneck:** Extracts high-level semantic representations.
* **Decoder:** Upsamples and aligns features to generate RGB colorized output.
* **Skip Connections:** Preserve fine spatial details from encoder to decoder.

---


## Training

* Trained with **MSE loss** on paired Sentinel-1 and Sentinel-2 images.
* Achieved progressively decreasing loss: **\~0.039 → 0.033 over increasing the number of epochs**.
* Optimized for robust generalization across various terrains.

---

## Usage

1. **Prepare Dataset:** Organize Sentinel-1 and Sentinel-2 images in separate folders.
2. **Load Data:** Use the provided `Sentinel12Dataset` class to create training and validation sets.
3. **Train Model:** Use the `UNetDenoiseRobust` architecture with MSE loss.
4. **Predict & Visualize:** Feed grayscale SAR images to get colorized outputs.

```python
s1, s2 = dataset[0]
s1_in = s1.unsqueeze(0).to(device)
pred = model(s1_in).cpu().squeeze(0)
```

---

## References

* U-Net: [Ronneberger et al., 2015](https://arxiv.org/abs/1505.04597)
* Sentinel-1 & Sentinel-2 datasets: [Copernicus Open Access Hub](https://scihub.copernicus.eu/)

---

## License

MIT License – free to use and modify for **research or educational purposes**.

---

