# Flower-Similarity

## Overview

This project aims to detect the similarity between pairs of flower images using a deep learning model. The dataset consists of 102 different flower categories with a total of 8,189 images. The model is trained to predict whether a pair of flower images are similar or not based on their labels.

## Dataset

- **Number of Categories**: 102
- **Total Images**: 8,189

The dataset is divided into training, validation, and testing sets. Each image is associated with a label indicating its flower category. The validation and test datasets include image pairs with labels indicating whether the pairs are similar (same category) or dissimilar (different categories).

## Methodology

### Loss Function

The model is trained using **Center Loss** to enhance its ability to distinguish between different categories while maintaining intra-class compactness.

### Training Procedure

1. **Data Splitting**: The dataset is divided into training, validation, and testing sets.
2. **Image Preprocessing**: Images are resized and normalized.
3. **Model Architecture**: A modified ResNeXt101 model with additional fully connected layers is used.
4. **Loss Functions**: Combination of **BCEWithLogitsLoss** for binary classification and **Center Loss** for better intra-class similarity.
5. **Optimizer**: Adam optimizer is used with learning rate scheduling for both the main model and the center loss component.

### Evaluation Metrics

- **ROC-AUC**: The performance is measured using the ROC-AUC score on the test dataset.

## Code Structure

- **Imports and Data Loading**: Libraries and data are loaded.
- **Dataset Preparation**: Custom dataset class to handle image pairs and labels.
- **Model Definition**: Definition of the Siamese network with ResNeXt101.
- **Training**: Training loop with loss calculation and optimizer updates.
- **Testing**: Evaluation of the model on the test set.
- **Visualization**: Functions to visualize image pairs and training history.



## Results

The model's performance is evaluated based on the ROC-AUC score, which is reported during the training process. The training and validation losses, ROC-AUC scores, and accuracy metrics are plotted for analysis.



You can download the dataset from the following link: [102Flowers](https://www.robots.ox.ac.uk/~vgg/data/flowers/102/)





