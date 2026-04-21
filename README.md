# Vehicle Classification Using Traditional Techniques and Deep Learning

🇺🇸 English | 🇧🇷 [Leia em Português](README.pt-BR.md)

---

## Overview

This project investigates a vehicle image classification task using both **traditional computer vision techniques** and **deep learning models**. The objective is to classify images into seven categories and compare approaches with manual descriptors against models with transfer learning and a custom CNN.

The project was developed based on **Vehicles Classification** from Kaggle, with **5,590 images** distributed across **7 classes**: **Auto Rickshaws, Bikes, Cars, Motorcycles, Planes, Ships and Trains**. The images were standardized to **224 × 224** and split into **70% training, 15% validation and 15% test**.

---

## Main Objectives

- Build a baseline with traditional feature extraction and classical machine learning
- Compare this baseline with deep learning approaches
- Analyze the impact of offline data augmentation
- Evaluate which strategy generalizes better for vehicle classification

---

## Dataset

- **Source:** Vehicles classification on Kaggle, available at the link: https://www.kaggle.com/datasets/mohamedmaher5/vehicle-classification/data
- **Number of classes:** 7
- **Total images:** 5,590
- **Input size:** 224 × 224
- **Training after augmentation:** 7,824 images in the augmented pipeline

---

## Methodology

### Traditional Approach

The traditional baseline uses manual visual descriptors and classical classifiers:

**Feature extraction**
- Color histogram in HSV
- HOG (Histogram of Oriented Gradients)
- LBP (Local Binary Patterns)
- Combinations between the descriptors

**Classifiers**
- SVM
- Random Forest
- KNN

### Deep Learning Approach

Three main models were explored:

- **MobileNetV2** with transfer learning
- **EfficientNetB0** with transfer learning
- **SmallCNN**, a custom CNN trained from scratch

---

## Pre-processing

- Resizing with padding to preserve the proportion
- Conversion to RGB
- Pixel normalization
- Conversions to HSV and grayscale for the manual descriptors
- Specific pre-processings for MobileNetV2 and EfficientNetB0

---

## Data Augmentation

Offline data augmentation was applied only in the training pipeline with transformations such as:

- Horizontal flip
- Rotation
- Translation
- Slight scale variations
- Gaussian noise
- Slight blur

The augmented pipeline expanded the training set by approximately **30%**, maintaining the same image resolution.

---

## Main Results

- Deep learning models consistently outperformed traditional methods
- **EfficientNetB0 trained on the original dataset** achieved the best overall result, with **98.69% accuracy**
- Classical data augmentation did **not** improve performance and caused a small drop in several models

---

## Repository Structure

```text
.
├── Equipe 9 2025-2-BCC-VC-ProjectPresentationTemplate.pdf
├── Grupo_9_2025_2_BCC_VC_ProjectTemplate.ipynb
├── README.md
└── README.pt-BR.md
```

---

## How to Run

### Option 1: Google Colab

1. Open the notebook in Google Colab
2. Upload your `kaggle.json` file when requested
3. Run the cells in order
4. The notebook downloads the dataset directly from Kaggle and runs the entire pipeline

### Option 2: Local Jupyter Environment

1. Create a Python environment
2. Install the necessary dependencies
3. Configure the Kaggle credentials
4. Run the notebook from start to finish

---

## Included Files

### `Grupo_9_2025_2_BCC_VC_ProjectTemplate.ipynb`
Main notebook with:
- dataset acquisition
- pre-processing
- manual feature extraction
- training of traditional models
- offline data augmentation
- training and evaluation of deep learning
- graphs and confusion matrices

### `Equipe 9 2025-2-BCC-VC-ProjectPresentationTemplate.pdf`
Final project presentation with summary of:
- motivation
- dataset
- methodology
- quantitative results
- qualitative examples
- conclusions and future work
