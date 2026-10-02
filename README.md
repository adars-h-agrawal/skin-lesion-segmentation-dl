# Deep Learning-Based Skin Lesion Segmentation

## Project Overview

This project investigates deep learning approaches for automatic segmentation of skin lesions from dermoscopic images.

The study uses the ISIC 2018 Skin Lesion Segmentation dataset and compares multiple segmentation architectures under a common preprocessing and evaluation protocol.

The proposed comparison includes:

1. MSRF-inspired CNN
2. U-Net
3. DeepLabV3+
4. SegFormer-B0

The primary objective is to study the effect of different architectural approaches on skin lesion segmentation quality.

---

## Dataset

**Dataset:** ISIC 2018 Skin Lesion Segmentation Task

The dataset contains dermoscopic skin lesion images together with corresponding expert-annotated binary segmentation masks.

### Input Configuration

- Image size: 256 × 256
- Input channels: RGB
- Output: Binary lesion segmentation mask

---

## Preprocessing

The preprocessing pipeline includes:

1. Image resizing to 256 × 256
2. Contrast enhancement using CLAHE
3. Black-hat based image enhancement
4. Image normalization
5. Binary mask preparation
6. Train-validation partitioning

The same preprocessing and evaluation protocol is maintained across the comparative models wherever applicable.

---

## Models

### 1. MSRF-Inspired CNN

The primary convolutional segmentation architecture uses multi-scale feature extraction, encoder-decoder processing, squeeze-and-excitation based feature recalibration, and feature fusion.

### 2. U-Net

A conventional encoder-decoder convolutional segmentation architecture using skip connections between corresponding encoder and decoder stages.

### 3. DeepLabV3+

A convolutional semantic segmentation architecture using atrous convolution and multi-scale contextual feature extraction.

### 4. SegFormer-B0

A lightweight Transformer-based semantic segmentation architecture used to introduce an attention-based architecture family into the comparison.

---

## Evaluation Metrics

The models are evaluated using:

- Dice coefficient
- Intersection over Union (IoU)
- Precision
- Recall

Additional qualitative analysis is performed using predicted segmentation masks and visual overlays.

---

## Experimental Setup

Experiments are conducted using GPU-based training.

The implementation and training experiments are executed using Kaggle notebooks.

The GitHub repository maintains:

- Project documentation
- Experimental configuration
- Training results
- Evaluation results
- Comparative results
- Literature review
- Project contribution record

---

## Project Status

| Model | Status |
|---|---|
| MSRF-inspired CNN | Completed |
| U-Net | In progress |
| DeepLabV3+ | Planned |
| SegFormer-B0 | Planned |

---

## Repository Organization

```text
docs/          Project and methodology documentation
results/       Experimental metrics
literature/    Literature review
figures/       Experimental visualizations
```

## Author

Adarsh Agrawal
MIT Manipal
Manipal Academy of Higher Education

## Academic Project

Deep Learning Project — ICT-4442
