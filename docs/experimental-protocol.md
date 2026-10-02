# Experimental Protocol

## Experimental Setup

All models are evaluated using the same dataset, preprocessing pipeline, validation split, random seed, and segmentation metrics.

- Dataset: ISIC 2018 Skin Lesion Segmentation Task 1
- Image size: 256 × 256
- Train/validation split: 80% / 20%
- Random seed: 42
- Prediction threshold: 0.5

## Evaluation Metrics

- **Dice:** Measures overlap between predicted and ground-truth masks.
- **IoU:** Measures intersection over union.
- **Precision:** Measures the proportion of predicted lesion pixels that are correct.
- **Recall:** Measures the proportion of lesion pixels correctly detected.

## Training Configuration

| Model | Epochs | Best Epoch | Validation Dice |
|---|---:|---:|---:|
| MSRF-inspired CNN | 125 | Not recorded | 0.8663 |
| U-Net | 20 | 20 | 0.8050 |
| DeepLabV3+ | 20 | 20 | 0.8724 |
| SegFormer-B0-style | 20 | 20 | 0.7836 |

The training budgets were not identical; therefore, results are treated as experimental comparisons rather than controlled claims about architecture superiority.

## Final Evaluation

The final comparison uses the held-out validation set and reports Dice, IoU, precision, and recall for all four models. Qualitative segmentation examples and metric comparison figures are also included in the repository.
