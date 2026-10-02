# Deep Learning-Based Skin Lesion Segmentation

## Comparative Study of CNN and Transformer Architectures

This project investigates deep learning approaches for automatic binary skin-lesion segmentation from dermoscopic images. The study compares convolutional and Transformer-based segmentation architectures under a common experimental protocol using the **ISIC 2018 Skin Lesion Segmentation Task 1** dataset.

The project focuses on accurate delineation of the lesion region from surrounding skin and examines how different architectural design choices affect segmentation quality.

---

## Problem Statement

Skin-lesion segmentation is an important component of computer-aided dermatological image analysis. Given a dermoscopic image, the objective is to automatically identify the pixels belonging to the lesion and separate them from the background skin.

The task is challenging because dermoscopic images may contain:

- Low contrast between lesion and surrounding skin
- Irregular lesion boundaries
- Variations in lesion size and shape
- Hair and other image artifacts
- Illumination and color variations
- Fine boundary structures that are difficult to preserve

Deep learning-based semantic segmentation can learn these spatial and contextual characteristics directly from image data.

---

## Objectives

The project has three primary objectives:

1. Develop a deep learning framework for automatic binary skin-lesion segmentation.
2. Compare convolutional and attention-based segmentation architectures under a common experimental protocol.
3. Analyze segmentation quality using overlap- and pixel-level evaluation metrics.

---

## Dataset

The project uses the **ISIC 2018 Skin Lesion Segmentation Task 1** dataset.

The dataset consists of dermoscopic RGB images together with corresponding expert-provided binary lesion masks.

### Dataset Configuration

| Property | Configuration |
|---|---|
| Dataset | ISIC 2018 Skin Lesion Segmentation Task 1 |
| Task | Binary semantic segmentation |
| Input | Dermoscopic RGB image |
| Target | Binary lesion mask |
| Image resolution | 256 × 256 |
| Training split | 80% |
| Validation split | 20% |
| Random seed | 42 |
| Prediction threshold | 0.5 |

The held-out validation split is used for quantitative evaluation.

---

## Preprocessing

A common preprocessing pipeline is applied before model training.

```text
Dermoscopic Image
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

For the MSRF-inspired architecture, an additional edge representation is generated and supplied as an auxiliary input.

```text
Preprocessed Image
        ↓
Edge Extraction
        ↓
Edge Map
        ↓
MSRF Auxiliary Input
```

Ground-truth masks are resized to the target resolution and represented as binary masks.

---

## Models

Four segmentation architectures are evaluated.

### 1. MSRF-Inspired CNN

The primary architecture is a multi-scale encoder-decoder CNN inspired by MSRF-Net.

The architecture incorporates:

- Convolutional feature extraction
- Multi-scale feature processing
- SE-based feature recalibration
- Encoder-decoder feature hierarchy
- Skip connections
- Edge-map auxiliary information

The architecture is intended to capture both lesion-level context and boundary-related information.

### 2. U-Net

U-Net is used as a conventional encoder-decoder CNN baseline.

Its main components include:

- Encoder for progressive feature extraction
- Decoder for spatial reconstruction
- Skip connections between corresponding encoder and decoder levels
- Batch normalization
- ReLU activation
- Sigmoid binary segmentation output

### 3. DeepLabV3+

DeepLabV3+ provides a CNN architecture designed to capture multi-scale contextual information.

The implementation uses:

- MobileNetV2 encoder
- Atrous Spatial Pyramid Pooling (ASPP)
- Low-level feature extraction
- Decoder-based feature refinement
- Sigmoid binary segmentation output

### 4. SegFormer-B0-Style Model

A lightweight Transformer-based segmentation architecture is included to introduce an attention-based comparison.

The model uses:

- Feature/patch embedding
- Transformer-style attention blocks
- Hierarchical feature representations
- Lightweight segmentation decoding
- Sigmoid binary segmentation output

---

## Experimental Protocol

The same base dataset, preprocessing pipeline, validation split, random seed, prediction threshold, and evaluation metrics are used across the experiments.

The training budgets were not identical across all models. Therefore, the results are presented as an experimental comparison rather than as a controlled claim that one architecture is universally superior to another.

### Evaluation Metrics

**Dice coefficient**

Measures the overlap between the predicted lesion mask and the ground-truth mask.

**Intersection over Union (IoU)**

Measures the intersection relative to the union of predicted and ground-truth lesion regions.

**Precision**

Measures the proportion of pixels predicted as lesion that are actually lesion pixels.

**Recall**

Measures the proportion of ground-truth lesion pixels correctly identified by the model.

---

## Results

The following results were obtained on the held-out validation set.

| Model | Epochs | Dice | IoU | Precision | Recall |
|---|---:|---:|---:|---:|---:|
| MSRF-inspired CNN | 125 | 0.8663 | 0.7664 | 0.9227 | 0.8224 |
| U-Net | 20 | 0.8050 | 0.7025 | 0.8472 | 0.8303 |
| DeepLabV3+ | 20 | 0.8724 | 0.7867 | 0.9046 | 0.8672 |
| SegFormer-B0-style | 20 | 0.7836 | 0.6997 | 0.9481 | 0.7467 |

These values are validation results and should be interpreted within the stated experimental setup and training budgets.

---

## Repository Structure

```text
skin-lesion-segmentation-dl/
│
├── README.md
├── CONTRIBUTIONS.md
│
├── docs/
│   ├── dataset-and-preprocessing.md
│   ├── experimental-protocol.md
│   ├── model-architectures.md
│   └── project-overview.md
│
├── figures/
│   ├── README.md
│   ├── qualitative_sample_1.png
│   ├── qualitative_sample_2.png
│   ├── qualitative_sample_3.png
│   ├── dice_comparison.png
│   ├── iou_comparison.png
│   └── all_metrics_comparison.png
│
├── literature/
│   └── literature-review.md
│
└── results/
    ├── msrf-results.csv
    ├── unet-results.csv
    ├── deeplabv3-results.csv
    ├── segformer-results.csv
    └── final-comparison.csv
```

---

## Visual Results

The `figures/` directory contains both quantitative and qualitative comparisons.

### Quantitative Comparisons

- Dice score comparison
- IoU comparison
- Combined metric comparison

### Qualitative Comparisons

Three validation examples are provided to visually compare predicted lesion masks across the evaluated architectures.

---

## Literature Review

The project literature review covers foundational and recent work in:

- U-Net-based segmentation
- DeepLabV3+
- Transformer-based segmentation
- MSRF-Net and multi-scale skin-lesion segmentation
- TransUNet
- UNet++
- Deep learning for skin-lesion analysis
- Medical image segmentation reviews

The complete literature summary is available in:

`literature/literature-review.md`

---

## Project Organization

The repository separates the project documentation, literature review, experimental results, and generated figures so that the methodology and results can be reviewed independently.

- `docs/` contains the dataset, preprocessing, methodology, and architecture documentation.
- `literature/` contains the literature review and research positioning.
- `results/` contains structured experimental results.
- `figures/` contains the generated visualizations.
- `CONTRIBUTIONS.md` records project responsibilities and completed work.

---

## Conclusion

The project provides a comparative study of four segmentation architecture families applied to binary skin-lesion segmentation. The experiments include a multi-scale CNN, a conventional U-Net, DeepLabV3+, and a lightweight Transformer-based model.

The resulting repository provides the dataset configuration, preprocessing methodology, architecture descriptions, literature review, quantitative results, and qualitative visual comparisons required to document the experimental study.
