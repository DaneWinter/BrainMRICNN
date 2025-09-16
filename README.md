# BrainMRIEfficientNet: EfficientNet-Inspired Architecture for Brain MRI Tumor Detection

## Overview

**BrainMRIEfficientNet** is a deep learning project implementing an EfficientNet-inspired convolutional neural network architecture optimized for brain MRI and other medical scanning tasks. The model utilizes compound scaling, residual connections, depthwise separable convolutions, and attention mechanisms (squeeze-and-excitation and spatial attention) to maximize accuracy and efficiency on medical imaging datasets.

This repository includes a Jupyter notebook of the model's implementation, and example usage for brain MRI tumor classification. The notebook can easily be ran inside of a free Google Colab session, or locally, for reproducing results. 

---

## Key Features

- **EfficientNet-Inspired Compound Scaling**: Balanced deepening, widening, and input resolution for efficient resource use.
- **Mobile Inverted Bottleneck Blocks**: Lightweight architecture for faster computation and reduced memory consumption.
- **Dilated Depthwise Separable Convolutions**: Wider view of input, but with lower computational and parameter cost while preserving feature richness.
- **Squeeze-and-Excitation (SE) Attention**: Adaptive channel recalibration boosts discriminative feature selection.
- **Spatial Attention**: Further focuses model on relevant anatomical regions, aiding tumor localization.
- **Batch Normalization and Residual Connections**: Enhanced training stability and improved gradient flow in deep architectures.

---

## Model Architecture

- **Input**: Preprocessed brain MRI images (e.g., size 224x224)
- **Backbone**: EfficientNet-inspired stack of mobile inverted bottleneck blocks with dilated, depthwise separable convolutions and attention modules
- **Attention Layers**: SE blocks for channel attention and spatial attention modules
- **Classification Head**: Dense layers with dropout for tumor classification (binary class: yes ~ tumor present, no ~ tumor not present)

---

## Strengths

- **Highly Efficient & Scalable**: Model contains only 5.6 million parameters - significantly smaller than other competitive models.
- **State-of-the-Art Feature Extraction**: Compound scaling and advanced attention mechanisms yield robust performance on diverse MRI scans.
- **Flexible**: Architecture/adaptations are applicable across a range of medical imaging tasks.
- **Fast Training and Inference**: Lower computational requirements compared to large vanilla CNNs or vision transformers.

---

## Limitations and Considerations

- **Overfitting Risk**: Powerful attention modules (SE, spatial) and aggressive scaling can cause overfitting if used with small or poorly augmented datasets.
- **Need for Careful Regularization**: Strong data augmentation, dropout, and validation splits are essential.
- **Batch Size Sensitivity**: Batch normalization can be unstable with small batch sizes typical of large MRI images—consider alternatives if necessary.

---

## When to Use This Model

- **Research in Brain Tumor Analysis**: When efficient, accurate diagnosis from MRI data is needed.
- **Edge Deployment**: Suitable for environments with constrained resources.
- **Projects Requiring Explainability**: Attention maps can highlight regions critical to automated diagnoses.

---

## Getting Started

Download the BrainCNN.ipynb file and open it in a free or paid Google Colab session. Model was trained using a paid-tier L4 gpu, but can run on free-tier gpus.

---
