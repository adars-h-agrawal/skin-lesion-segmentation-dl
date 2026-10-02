# Dataset and Preprocessing

## Dataset

**ISIC 2018 Skin Lesion Segmentation Task 1** is used for binary skin-lesion segmentation.

- Input: dermoscopic RGB images
- Target: binary lesion masks
- Resolution: 256 × 256
- Split: 80% training / 20% validation
- Random seed: 42

## Preprocessing Pipeline

```text
ISIC Image
    ↓
Resize to 256 × 256
    ↓
CLAHE Contrast Enhancement
    ↓
Black-Hat Morphological Processing
    ↓
Normalization
    ↓
Model Input
```

For the MSRF-inspired model, an additional edge map is generated:

```text
Preprocessed Image
    ↓
Edge Extraction
    ↓
Edge Map
    ↓
MSRF Auxiliary Input
```

## Mask Processing

Ground-truth masks are resized to 256 × 256 and converted to binary masks:

- `0` → Background
- `1` → Lesion

Model predictions are converted to binary masks using a threshold of `0.5`.

## Model Inputs

| Model | Input |
|---|---|
| MSRF-inspired CNN | RGB image + edge map |
| U-Net | RGB image |
| DeepLabV3+ | RGB image |
| SegFormer-B0-style | RGB image |

## Summary

The same base preprocessing pipeline and validation split are used across the experiments. Quantitative results reported in the repository correspond to the held-out validation set.
