# Betel Leaf Disease Diagnosis Using an Integrated Deep Learning Framework

## Overview

This project presents an integrated deep learning framework for automated betel leaf disease classification, lesion segmentation, and quantitative lesion-burden estimation. Using RGB images of bacterial, fungal, and healthy betel leaves from Bangladesh, the framework combines disease classification, pixel-level lesion segmentation, and geometric–spatial feature extraction.

## Research Pipeline

Our integrated function successfully produced three outputs from one image:
Classification model classfies the disease category > segmentation model segments leaf and lesion area, and image processing calculates the number of lesion pixels and leaf pixels for semantic lesion burden calculation.

1. **Disease Classification**: EfficientNet-B0 for three-class disease classification.

2. **Leaf and Lesion Segmentation**: EfficientNet-B0 U-Net for pixel-level leaf and lesion segmentation.

3. **Geometric Lesion Representation**: Extraction of lesion area, compactness, component count, spatial distribution, and other geometric characteristics.

4. **Integrated Diagnosis**: Sequential integration of classification, segmentation, and geometric feature extraction.

5. **Quantitative Lesion Assessment**: Estimation of lesion burden as the percentage of predicted leaf area occupied by predicted lesions.

The classification and segmentation models are independently trained and integrated during inference.

## Dataset & Labelling
The dataset was obtained from the Project AgML repository. Three classes were retained: bacterial, fungal, and healthy.

ImageHash, Pillow, and manual inspection were used for duplicate and image-quality screening, resulting in a final dataset of 720 images.

Leaf and lesion regions were annotated using LabelMe. Its SAM2-based AI-assisted mask creation feature was used to accelerate annotation, followed by manual corrections where necessary.

## Models and Technologies

**Classification**: ResNet-50 and EfficientNet-B0

**Segmentation**: EfficientNet-B0 U-Net

**Image Processing**: NumPy, Pillow, SciPy, and scikit-image

**Deep Learning Framework**: PyTorch

**Development Environment**: Google Colab

EfficientNet-B0 was selected as the final classification model after comparison with ResNet-50.

## Held-Out Test Results

**Disease classification**:


| Metric | ResNet-50 | EfficientNet-B0 |
|:---|---:|---:|
| Macro Precision | 97.30% | 98.20% |
| Macro Recall | 97.22% | 98.20% |
| Macro-F1 | 97.27% | 98.20% |

Segmentation performance:

Threshold: 0.5


| Metric | Leaf Segmentation | Lesion Segmentation |
|:---|---:|---:|
| Dice | 0.9925 | 0.9171 |
| IoU | 0.9850 | 0.8469 |
| Precision | 0.9886 | 0.9485 |
| Recall | 0.9963 | 0.8877 |

LESION BURDEN ESTIMATION
Pearson Correlation: .99
MAE 0.29
RMSE 0.95

HEALTHY IMAGE FALSE POSITIVES
Mean FP area: 0.008985%
Images with FP: 2 / 37

Research Contribution

The framework integrates disease recognition with lesion localization and quantitative geometric characterization, providing complementary information beyond conventional image-level classification. It also evaluates the agreement between predicted and ground-truth lesion measurements.

