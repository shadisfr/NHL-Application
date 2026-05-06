# Age-Detection

## Introduction
Age detection is a complex challenge in data science with applications in surveillance, social media, marketing, and healthcare. This project proposes a novel method combining effective preprocessing techniques with advanced neural network architectures to predict an individual's age with improved accuracy.

## Related Work
Previous approaches to age detection include:
- **Convolutional Neural Networks (CNNs)**: For automatic feature extraction from images.
- **Transfer Learning**: Fine-tuning pre-trained models on new datasets.
- **Ensemble Learning**: Combining multiple models to improve performance.

Our method builds on these techniques, addressing limitations and enhancing accuracy.

## Proposed Method
The proposed approach involves the following steps:

1. **Data Cleaning**: Validated paths, removed duplicates, and ensured data consistency.
2. **Image Preprocessing**: Resized images to 64x64 pixels and normalized pixel values.
3. **Face Detection**: Used dlib's frontal face detector.
4. **Face Alignment & Normalization**: Corrected face orientation and lighting variations.
5. **Data Augmentation**: Applied random rotations to increase model robustness.
6. **Feature Extraction**:
   - **Wrinkle Features**: Detected using Canny edge detection.
   - **Hair Color**: Extracted using HSV color space and masking.
   - **Facial Landmarks**: Detected using dlib’s facial landmark predictor.
   - **Eye Openness Detection**: Planned but not yet implemented.
7. **Data Exclusion**: Removed incompatible images to maintain data quality.

## Neural Network Architecture
### CNN Model
- **Layers**: Two convolutional layers followed by max-pooling, a dense layer, and final output layer.
- **Activation Functions**: ReLU for hidden layers, linear for output.

### VGGFace Model
- **Pre-trained VGGFace**: Used for feature extraction with a dense layer added for regression.
- **Layers**: Similar to the CNN model but with VGGFace features.

### Training
- **Optimizer**: Adam
- **Loss Function**: Mean Squared Error (MSE)
- **Epochs**: 10
- **Batch Size**: 32
- **Validation Split**: 0.2

## Performance Metrics
- **Mean Absolute Error (MAE)**
- **Mean Squared Error (MSE)**
- **F1 Score**: For binary classification task

## Results
- **CNN vs. VGGFace**: CNN achieved slightly lower MAE and MSE, indicating better performance.
- **Normalization Impact**: Normalized face images improved model performance compared to original images.

## Discussion
- **Suitability of Deep Neural Networks**: CNNs and pre-trained models are effective for age detection.
- **Benefits**: Combines CNN features and pre-existing knowledge from VGGFace. Multi-modal approach including additional features.
- **Limitations**: Uneven age distribution in dataset might affect performance. Future work could address this with data balancing techniques.



You can download the dataset from the following link: [Age Detection](https://www.kaggle.com/datasets/trainingdatapro/age-detection-human-faces-18-60-years)

