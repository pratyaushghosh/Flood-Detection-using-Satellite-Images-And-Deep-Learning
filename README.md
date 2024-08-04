# 🌧️ Flood Detection Using Satellite Images And Deep Learning 🌊

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## Overview

Floods present significant challenges for detection and delineation, especially when cloud cover obscures optical imagery. This project aims to enhance flood detection by leveraging a multi-sensor approach, combining Sentinel-1 (S1) and Sentinel-2 (S2) satellite data through deep learning techniques.

## Table of Contents

- [Introduction](#introduction)
- [Dataset](#dataset)
- [Methodology](#methodology)
  - [Custom CNN](#custom-cnn)
  - [VGG16 CNN](#vgg16-cnn)
  - [AlexNet CNN](#alexnet-cnn)
- [Data Pre-processing](#data-pre-processing)
- [Results](#results)
- [How to Use](#how-to-use)
- [Contributing](#contributing)
- [License](#license)

## Introduction

Cloudy images pose challenges for accurate flood detection and delineation. While S2 imagery is effective for flood detection, traditional cloud removal approaches are unsuitable for short-lived events like floods. S1 imagery alone struggles to differentiate between water and non-water pixels, particularly in urban areas. This project explores a multi-sensor approach to enhance flood detection using fused S1 and S2 data and deep learning models.

## Dataset

We utilize the [Sen1Floods11 dataset](https://mlhub.earth/data/sen12floods), which provides mono-temporal S1 and S2 image pairs sampled within two days from 11 global flood events. The dataset includes semi-manually annotated labels classifying each pixel as water, no water, or no data (cloud-covered pixels in S2).

## Methodology

### Custom CNN

A sequential model designed for feature extraction and classification. It consists of convolutional layers with ReLU activation, pooling layers, and dense layers, concluding with a softmax layer for classification.

### VGG16 CNN

A deep convolutional neural network with 19 layers, including 16 convolutional layers and 3 fully connected layers. Known for its uniform structure and small filter sizes, VGG16 captures hierarchical features of increasing complexity.

### AlexNet CNN

A pioneering CNN architecture with 8 layers, including 5 convolutional layers and 3 fully connected layers. AlexNet introduced ReLU activation functions and dropout regularization, revolutionizing deep learning for image classification.

## Data Pre-processing

Pre-processing steps include cleaning and transforming the dataset, removing empty folders and images with all-zero pixel values. Selected spectral bands (2, 3, 4, and 8) are stacked together to create multispectral images for analysis.

## Results

The models are trained and evaluated on the cleaned dataset, achieving significant improvements in flood detection accuracy through the fusion of S1 and S2 data.

## How to Use

1. **Clone the repository**:
    ```bash
    git clone https://github.com/pratyaushghosh/Flood-Detection-using-Satellite-Images-And-Deep-Learning.git
    cd flood-detection-multisensor
    ```

2. **Install dependencies**:
    ```bash
    pip install -r requirements.txt
    ```

3. **Run the pre-processing script**:
    ```bash
    python pre_processing.py
    ```

4. **Train the model**:
    ```bash
    python train_model.py
    ```

5. **Evaluate the model**:
    ```bash
    python evaluate_model.py
    ```

## Contributing

We welcome contributions to improve this project. Please fork the repository and create a pull request with your changes.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

Enhance flood detection accuracy by combining the power of Sentinel-1 and Sentinel-2 imagery with deep learning models. 🌍🚀

For detailed documentation and further reading, please refer to the project [Wiki](https://github.com/yourusername/flood-detection-multisensor/wiki).
