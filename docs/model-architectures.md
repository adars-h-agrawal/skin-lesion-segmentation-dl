# Model Architectures

## 1. MSRF-Inspired CNN

The primary architecture is a multi-scale encoder-decoder CNN inspired by MSRF-Net.

- Convolutional feature extraction
- Multi-scale feature processing
- SE-based feature recalibration
- Encoder-decoder structure
- Skip connections
- Edge-map auxiliary input
- Sigmoid segmentation output

## 2. U-Net

U-Net is used as the conventional CNN baseline.

- Encoder-decoder architecture
- Progressive downsampling and upsampling
- Skip connections between encoder and decoder
- Batch normalization and ReLU activations
- Sigmoid output for binary segmentation

## 3. DeepLabV3+

DeepLabV3+ provides a CNN architecture with multi-scale contextual feature extraction.

- MobileNetV2 encoder
- Atrous Spatial Pyramid Pooling (ASPP)
- Low-level feature fusion
- Decoder-based refinement
- Sigmoid binary segmentation output

## 4. SegFormer-B0-Style Model

A lightweight Transformer-based segmentation model is included to provide an attention-based comparison.

- Patch/feature embedding
- Transformer-style attention blocks
- Hierarchical feature processing
- Lightweight decoder
- Sigmoid binary segmentation output

## Architecture Comparison

| Model | Architecture Family | Main Feature |
|---|---|---|
| MSRF-inspired CNN | CNN | Multi-scale + edge-guided features |
| U-Net | CNN | Encoder-decoder + skip connections |
| DeepLabV3+ | CNN | Atrous multi-scale context |
| SegFormer-B0-style | Transformer | Attention-based feature modelling |
