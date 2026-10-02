# Project Overview

## Title

**Deep Learning-Based Skin Lesion Segmentation: A Comparative Study of CNN and Transformer Architectures**

## Problem

Automatic skin-lesion segmentation is a pixel-level computer vision task in which the lesion region must be separated from the surrounding skin. Dermoscopic images contain variations in illumination, texture, lesion appearance, and boundaries, making accurate segmentation challenging.

## Dataset

The project uses the **ISIC 2018 Skin Lesion Segmentation Task 1** dataset containing dermoscopic images and corresponding binary lesion masks.

## Approach

The project compares four segmentation architectures:

1. MSRF-inspired CNN
2. U-Net
3. DeepLabV3+
4. SegFormer-B0-style model

A common preprocessing and evaluation protocol is used to make the experimental results comparable.

## Objectives

- Develop a deep learning framework for automatic skin-lesion segmentation.
- Compare CNN-based and Transformer-based segmentation architectures.
- Analyze segmentation quality using Dice, IoU, precision, and recall.

## Results Summary

| Model | Dice | IoU | Precision | Recall |
|---|---:|---:|---:|---:|
| MSRF-inspired CNN | 0.8663 | 0.7664 | 0.9227 | 0.8224 |
| U-Net | 0.8050 | 0.7025 | 0.8472 | 0.8303 |
| DeepLabV3+ | 0.8724 | 0.7867 | 0.9046 | 0.8672 |
| SegFormer-B0-style | 0.7836 | 0.6997 | 0.9481 | 0.7467 |

All reported values are from the held-out validation set.
