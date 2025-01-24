## Overview

This project implements **nuclear segmentation** using the **U-Net architecture**, a deep learning model specifically designed for semantic segmentation tasks. The goal of this project is to accurately segment nuclei from histopathological images to aid in the analysis of medical images, especially in cancer diagnosis and cell counting.

## Project Description

This repository provides an end-to-end pipeline for **nuclei segmentation** using U-Net, a deep convolutional neural network designed for biomedical image segmentation. The model is trained on histopathological images and is capable of segmenting the individual nuclei present in the images.

Key Features:
- U-Net architecture for segmentation.
- Preprocessing of images and annotations.
- Model training with validation and testing.
- Performance evaluation with common metrics like IoU, Dice score, etc.

## Model Architecture

The U-Net model consists of two main parts:
1. **Encoder (Contracting Path)**: This part captures context through convolutional layers and downsampling operations.
2. **Decoder (Expansive Path)**: This part enables precise localization by upsampling and concatenating feature maps from the encoder.

The model architecture uses **skip connections** to combine feature maps from the contracting and expansive paths, which helps retain high-resolution details during the segmentation process.

## U-Net Architecture Details

- **Input**: Image of shape `(height, width, channels)`
- **Output**: Segmentation mask of shape `(height, width, 1)` for binary segmentation.
- **Contracting Path**:
  - Series of convolutional layers followed by max-pooling operations.
  - Each block captures increasing levels of feature abstraction.
- **Bottleneck**: The deepest layer of the network that contains the most abstract features.
- **Expansive Path**:
  - Upsampling followed by convolution to recover spatial information.
  - Skip connections from the contracting path are concatenated to preserve fine-grained features.
- **Final Layer**: A convolutional layer that outputs a binary mask, indicating the presence of nuclei.

## Evaluation

The model's performance is evaluated using the following metrics:
- **Dice Similarity Coefficient (DSC)**: Measures the overlap between the predicted and ground truth masks. Higher values indicate better performance.
- **Intersection over Union (IoU)**: Measures the intersection of predicted and true positives relative to the union of predicted and true positives.
- **Pixel Accuracy**: Measures the percentage of correctly classified pixels in the segmentation mask.
