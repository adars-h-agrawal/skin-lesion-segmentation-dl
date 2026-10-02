# Project Overview

## Title

Deep Learning-Based Skin Lesion Segmentation: A Comparative Study of CNN and Transformer Architectures

## Problem Statement

Accurate delineation of skin lesions from dermoscopic images is an important step in computer-aided dermatological image analysis. Manual segmentation can be time-consuming and may exhibit inter-observer variation.

The project investigates automated lesion segmentation using deep learning architectures with different feature extraction and representation mechanisms.

## Objectives

1. Develop a deep learning framework for automatic skin lesion segmentation.

2. Compare convolutional and attention-based segmentation architectures under a common experimental protocol.

3. Analyze segmentation quality using overlap-based and pixel-level evaluation metrics.

## Dataset

The experiments use the ISIC 2018 Skin Lesion Segmentation dataset.

The dataset provides dermoscopic images and corresponding expert-generated binary lesion masks.

## Architecture Families

The comparison covers:

- Multi-scale convolutional segmentation
- Conventional encoder-decoder CNN segmentation
- Atrous convolution based semantic segmentation
- Transformer-based semantic segmentation

## Expected Analysis

The final analysis will compare the models using:

- Dice coefficient
- IoU
- Precision
- Recall

Qualitative segmentation examples will also be examined to understand differences in lesion boundary preservation and segmentation quality.
