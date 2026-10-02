# Model Architectures

## 1. MSRF-Inspired CNN

The primary segmentation model follows a multi-scale convolutional encoder-decoder design.

The architecture incorporates:

- Convolutional feature extraction
- Encoder-decoder processing
- Multi-scale feature representation
- Squeeze-and-Excitation based feature recalibration
- Skip-based feature fusion
- Pixel-wise sigmoid segmentation output

The model produces a binary segmentation mask corresponding to the lesion region.

---

## 2. U-Net

U-Net follows the classical encoder-decoder segmentation structure.

### Encoder

The encoder progressively extracts higher-level features while reducing spatial resolution.

### Decoder

The decoder progressively restores spatial resolution.

### Skip Connections

Features from corresponding encoder stages are concatenated with decoder features to preserve spatial information and improve boundary localization.

### Output

A 1 × 1 convolution followed by sigmoid activation produces the binary segmentation mask.

---

## 3. DeepLabV3+

DeepLabV3+ uses convolutional feature extraction together with atrous convolution to capture contextual information at multiple spatial scales.

The architecture combines:

- Atrous convolution
- Multi-scale contextual representation
- Encoder-decoder refinement
- High-resolution boundary recovery

It provides a CNN-based comparison against the MSRF-inspired model and U-Net.

---

## 4. SegFormer-B0

SegFormer-B0 introduces a Transformer-based architecture into the comparison.

The model uses attention-based feature representation and a lightweight segmentation decoder.

This provides an architectural contrast to the convolution-based models.

---

## Architecture Comparison

| Model | Architecture Family | Main Characteristic |
|---|---|---|
| MSRF-inspired CNN | CNN | Multi-scale feature extraction |
| U-Net | CNN | Encoder-decoder with skip connections |
| DeepLabV3+ | CNN | Atrous multi-scale context |
| SegFormer-B0 | Transformer | Attention-based representation |
