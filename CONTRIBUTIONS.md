# Contributions

## Project Member

This is an individual deep learning project.

| Member | Registration Number | Responsibility |
|---|---|---|
| Adarsh Agrawal | 230911264 | End-to-end project development |

---

## Overall Contribution

The project was completed as an individual study covering the complete workflow from dataset preparation and literature review through model development, experimentation, evaluation, visualization, and documentation.

The work includes the following major components:

1. Problem definition and project planning
2. Dataset identification and preparation
3. Image preprocessing
4. Ground-truth mask processing
5. Model architecture development
6. Model training
7. Validation and quantitative evaluation
8. Qualitative result generation
9. Literature review
10. Experimental documentation
11. Result organization
12. Repository organization

---

## Dataset and Preprocessing

The following tasks were completed:

- Identified the ISIC 2018 Skin Lesion Segmentation Task 1 dataset.
- Prepared dermoscopic RGB images for segmentation experiments.
- Resized images to 256 × 256.
- Applied CLAHE-based contrast enhancement.
- Applied black-hat morphological processing.
- Normalized image inputs.
- Prepared corresponding binary lesion masks.
- Created the 80% training / 20% validation split.
- Used a fixed random seed of 42 for reproducibility.
- Generated edge representations for the MSRF-inspired model.

---

## Model Development

### MSRF-Inspired CNN

Responsibilities included:

- Designing the multi-scale encoder-decoder segmentation pipeline.
- Integrating convolutional feature extraction.
- Incorporating SE-based feature recalibration.
- Implementing skip connections.
- Integrating the edge-map auxiliary input.
- Configuring the training and validation pipeline.
- Training the model and recording validation metrics.

**Status:** Completed

### U-Net

Responsibilities included:

- Implementing the encoder-decoder architecture.
- Configuring convolutional blocks and skip connections.
- Preparing the model for the common preprocessing pipeline.
- Training the model.
- Recording validation metrics.

**Status:** Completed

### DeepLabV3+

Responsibilities included:

- Implementing the DeepLabV3+ segmentation architecture.
- Integrating a MobileNetV2 encoder.
- Implementing Atrous Spatial Pyramid Pooling.
- Integrating low-level and high-level features.
- Configuring the decoder.
- Training and evaluating the model.

**Status:** Completed

### SegFormer-B0-Style Model

Responsibilities included:

- Implementing the lightweight Transformer-style segmentation architecture.
- Integrating feature embedding and attention-based processing.
- Configuring the segmentation decoder.
- Training the model.
- Recording validation metrics.

**Status:** Completed

---

## Experimental Evaluation

The following evaluation activities were completed:

- Validation-set inference for the trained models.
- Dice coefficient calculation.
- IoU calculation.
- Precision calculation.
- Recall calculation.
- Structured CSV result generation.
- Final cross-model metric comparison.
- Qualitative segmentation comparison on validation samples.

The evaluation protocol uses a prediction threshold of 0.5 for converting model outputs into binary masks.

---

## Results Generated

Individual result files were organized for each architecture:

```text
results/
├── msrf-results.csv
├── unet-results.csv
├── deeplabv3-results.csv
├── segformer-results.csv
└── final-comparison.csv
```

The final comparison contains the recorded validation metrics for all four architectures.

---

## Figures and Visualization

The following visualizations were generated:

- Three qualitative segmentation comparison panels
- Dice score comparison
- IoU comparison
- Combined metric comparison

These figures were organized under the `figures/` directory.

---

## Literature Review

The literature review covered foundational and recent work related to:

- U-Net
- DeepLabV3+
- SegFormer
- MSRF-Net
- TransUNet
- UNet++
- Skin-lesion segmentation
- Medical image segmentation
- Deep learning-based skin-lesion analysis

The literature was organized into a structured comparison covering:

- Paper and publication year
- Method
- Dataset/application
- Key findings
- Relevance to the project

The complete review is stored in:

`literature/literature-review.md`

---

## Documentation

Project documentation was prepared for:

- Dataset and preprocessing
- Experimental protocol
- Model architectures
- Project overview
- Literature review
- Figures
- Contributions

The documentation was organized so that the methodology, experiments, results, and project responsibilities can be reviewed separately.

---

## Contribution Summary

| Component | Contributor | Status |
|---|---|---|
| Project planning | Adarsh Agrawal | Completed |
| Dataset preparation | Adarsh Agrawal | Completed |
| Preprocessing pipeline | Adarsh Agrawal | Completed |
| MSRF-inspired CNN | Adarsh Agrawal | Completed |
| U-Net | Adarsh Agrawal | Completed |
| DeepLabV3+ | Adarsh Agrawal | Completed |
| SegFormer-B0-style model | Adarsh Agrawal | Completed |
| Model evaluation | Adarsh Agrawal | Completed |
| Result generation | Adarsh Agrawal | Completed |
| Qualitative visualization | Adarsh Agrawal | Completed |
| Literature review | Adarsh Agrawal | Completed |
| Documentation | Adarsh Agrawal | Completed |
| Repository organization | Adarsh Agrawal | Completed |

---

## Individual Project Declaration

All project components listed above were carried out by the individual project member, Adarsh Agrawal (230911264), as part of the Deep Learning project.

The contribution record reflects the work completed across dataset preparation, model development, experimentation, evaluation, literature review, visualization, and documentation.
