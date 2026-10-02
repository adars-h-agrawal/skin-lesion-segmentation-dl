# Dataset and Preprocessing

## Dataset

The project uses the **ISIC 2018 Skin Lesion Segmentation Task** dataset.

The dataset consists of dermoscopic skin lesion images and corresponding expert-annotated binary segmentation masks.

## Input Representation

All input images are resized to:

**256 × 256 × 3**

The segmentation target is:

**256 × 256 × 1**

representing the binary lesion mask.

---

## Preprocessing Pipeline

The preprocessing pipeline consists of the following stages.

### 1. Image Resizing

All dermoscopic images are resized to **256 × 256 pixels** to provide a consistent input resolution.

### 2. CLAHE Enhancement

**Contrast Limited Adaptive Histogram Equalization (CLAHE)** is applied to improve local contrast and enhance lesion-related visual structures.

### 3. Black-Hat Enhancement

**Black-hat morphological processing** is used as part of the image enhancement procedure to emphasize relevant dark structures and improve visual representation.

### 4. Normalization

Pixel intensities are converted to floating-point representation and normalized to the range:

**[0, 1]**

### 5. Mask Processing

Ground-truth segmentation masks are resized using **nearest-neighbor interpolation** and converted into binary masks.

### 6. Dataset Partition

The available training data is partitioned into **training and validation subsets** using a fixed random seed to maintain consistency between experiments.

---

## Experimental Consistency

The same dataset partition and evaluation metrics are used for the comparative experiments wherever applicable.

This allows model performance to be compared under a consistent experimental setting.
