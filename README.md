# Video Classification Using GRU with Custom ResNet-50 Feature Extraction

## Project Overview

This project implements a video classification model using GRU layers. The model extracts features from video frames using a custom-built **ResNet-50 architecture** (not pre-trained) and then classifies the videos based on these extracted features. The solution achieves a **validation accuracy of 96.3%** and a **test accuracy of 91.8%**.

## Table of Contents
- [Introduction](#introduction)
- [Dataset](#dataset)
- [Model Architecture](#model-architecture)
- [Training Process](#training-process)
- [Feature Extraction](#feature-extraction)
- [Normalization](#normalization)


## Introduction

This project tackles the challenge of classifying video sequences. The key steps include feature extraction from the video frames using a custom ResNet-50 model and sequence modeling using GRU for video classification.

## Dataset

- The dataset consists of video sequences.
- Features were extracted from the frames using a custom ResNet-50 model.
- The dataset was split into training, validation, and test sets.
  
## Model Architecture

The model uses a custom-built ResNet-50 for feature extraction. The extracted features are passed into an GRU layer to capture the temporal dependencies across frames.

- **ResNet-50**: Built from scratch for feature extraction.
- **GRU**: Used to process the sequence of extracted features and classify videos.

### Architecture Flow
1. **ResNet-50** for frame-level feature extraction.
2. **GRU** layer for sequence modeling across extracted features.
3. Fully connected layers for classification.

## Training Process

- The videos were broken down into frames, and frame-level features were extracted using the ResNet-50 model.
- GRU was used to model the sequence of these extracted features.
- A combination of cross-entropy loss and Adam optimizer was used for training the model.
- **Learning Rate Scheduling**: Gradual learning rate decay was applied during training.
  
## Feature Extraction

Each video was processed frame by frame. The ResNet-50 model extracted **2048-dimensional feature vectors** from each frame. The extracted features were then reshaped and fed into the GRU model.

## Normalization

The extracted features were normalized using MinMax scaling, which was essential to ensure that the features fell within a suitable range for effective training.

