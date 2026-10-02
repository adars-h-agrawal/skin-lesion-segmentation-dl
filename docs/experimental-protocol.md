# Experimental Protocol

## Objective

The experiments are designed to compare multiple segmentation architectures under a common evaluation protocol.

## Input

- Resolution: 256 × 256
- Channels: 3
- Task: Binary segmentation

## Training

The models are trained using the prepared ISIC 2018 training data.

For preliminary comparative experiments, a limited training schedule is used to obtain model performance without extensive hyperparameter optimization.

## Validation

A fixed validation partition is used for model comparison.

The validation partition is generated using a fixed random seed to improve reproducibility.

## Metrics

The following metrics are recorded:

### Dice Coefficient

Measures overlap between the predicted segmentation and the ground-truth mask.

### Intersection over Union

Measures the ratio between intersection and union of predicted and ground-truth regions.

### Precision

Measures the proportion of predicted lesion pixels that correspond to actual lesion pixels.

### Recall

Measures the proportion of actual lesion pixels correctly identified by the model.

## Qualitative Evaluation

Selected segmentation outputs are visualized using:

- Input image
- Ground-truth mask
- Predicted segmentation
- Prediction overlay

## Comparative Evaluation

The final comparison will place all proposed architectures under the same metric framework.

The results will be summarized in a single comparison table.
