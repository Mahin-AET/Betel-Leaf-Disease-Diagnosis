# Betel Leaf Disease Diagnosis Using an Integrated Deep Learning Framework

Overview

This project presents an integrated deep learning framework for automated betel leaf disease classification, lesion segmentation, and quantitative lesion-burden estimation. Using RGB images of bacterial, fungal, and healthy betel leaves from Bangladesh, the framework combines disease classification, pixel-level lesion segmentation, and geometric–spatial feature extraction.

# Research Pipeline

1. Disease Classification: EfficientNet-B0 for three-class disease classification.

2. Leaf and Lesion Segmentation: EfficientNet-B0 U-Net for pixel-level leaf and lesion segmentation.

3. Geometric Lesion Representation: Extraction of lesion area, compactness, component count, spatial distribution, and other geometric characteristics.

4. Integrated Diagnosis: Sequential integration of classification, segmentation, and geometric feature extraction.

5. Quantitative Lesion Assessment: Estimation of lesion burden as the percentage of predicted leaf area occupied by predicted lesions.

The classification and segmentation models are independently trained and integrated during inference.
