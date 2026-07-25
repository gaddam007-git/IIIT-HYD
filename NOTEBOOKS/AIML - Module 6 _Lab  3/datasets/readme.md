# Datasets and Input Files Used

This notebook demonstrates various Convolutional Neural Network (CNN) concepts, including convolution operations, CNN training, and transfer learning. Three different inputs are used throughout the notebook.

---

# 1. lotus.jpg

## Description
`lotus.jpg` is a single RGB image used to demonstrate the basic operation of convolution in CNNs. It is **not a dataset**, but an input image used for visualization.

## Purpose
- Demonstrate convolution operation
- Understand feature extraction
- Observe the effects of different padding values
- Observe the effects of different stride values

## Input
- Single RGB image (`lotus.jpg`)

## Processing
- Read image using OpenCV
- Convert BGR to RGB
- Normalize pixel values
- Convert image to PyTorch tensor
- Apply convolution filters
- Experiment with different padding and stride values

## Output
- Feature maps after convolution
- Images showing the effect of padding
- Images showing the effect of stride

---

# 2. MNIST Dataset

## Description
The MNIST (Modified National Institute of Standards and Technology) dataset is a benchmark dataset containing grayscale images of handwritten digits.

## Dataset Information

- Total Classes: 10
- Classes: Digits 0–9
- Training Images: 60,000
- Test Images: 10,000
- Image Size: 28 × 28 pixels
- Channels: 1 (Grayscale)

## Dataset Source

Loaded directly using TorchVision:

```python
torchvision.datasets.MNIST()
```

## Purpose

The MNIST dataset is used to:

- Build a CNN from scratch
- Train the CNN
- Evaluate CNN performance
- Learn feature extraction using convolution and pooling layers

## Input

- Handwritten digit images

## Processing

1. Download MNIST dataset
2. Convert images into tensors
3. Create DataLoaders
4. Train CNN
5. Compute loss
6. Backpropagation
7. Update model weights
8. Test the trained model

## Output

- Training Loss
- Training Accuracy
- Test Accuracy
- Predicted digit classes (0–9)

---

# 3. German Traffic Sign Recognition Benchmark (GTSRB)

## Description

The German Traffic Sign Recognition Benchmark (GTSRB) is a multiclass image classification dataset containing traffic sign images.

## Dataset Information

- Total Classes: 43
- Image Type: RGB
- Application: Traffic Sign Recognition

## Purpose

The dataset is used for:

- Transfer Learning
- Fine-tuning pretrained CNN models
- Feature Extraction
- Performance comparison between pretrained models

## Models Used

- ResNet18 (Original Notebook)
- MobileNetV2 (Modified Experiment)

## Input

Traffic sign images belonging to 43 different classes.

## Processing

1. Load traffic sign images
2. Apply preprocessing and transformations
3. Create Training, Validation, and Test DataLoaders
4. Load pretrained CNN model
5. Fine-tune the model
6. Perform feature extraction
7. Evaluate model performance

## Output

### Fine-Tuning Results (MobileNetV2)

- Initial Test Accuracy: 2.30%
- Best Validation Accuracy: 100.00%
- Final Test Accuracy: 89.70%

### Feature Extraction Results

- Initial Test Accuracy: 2.10%
- Best Validation Accuracy: 61.80%
- Final Test Accuracy: 35.00%

---

# Overall Workflow

## Part 1 – Convolution Demonstration

```
lotus.jpg
      │
      ▼
Convolution
      │
Padding & Stride
      │
      ▼
Feature Maps
```

## Part 2 – CNN Training

```
MNIST Dataset
      │
      ▼
CNN
      │
Training
      │
      ▼
Digit Classification
```

## Part 3 – Transfer Learning

```
GTSRB Dataset
      │
      ▼
Pretrained MobileNetV2
      │
Fine-Tuning / Feature Extraction
      │
      ▼
Traffic Sign Classification
```

---

# Summary

| Input | Type | Purpose | Output |
|--------|------|---------|--------|
| lotus.jpg | Single Image | Demonstrate convolution, padding and stride | Feature maps |
| MNIST | Image Dataset | CNN training from scratch | Digit classification (0–9) |
| GTSRB | Image Dataset | Transfer learning | Traffic sign classification (43 classes) |
