# Cats vs Dogs Classification with CNN

## Project Overview
This project addresses a **binary image classification task**: distinguishing between cats and dogs
using a Convolutional Neural Network trained from scratch.

The focus is on:
- dataset preparation and labeling,
- building a simple CNN architecture,
- analyzing overfitting and class imbalance,
- evaluating model performance beyond raw accuracy.

---

## Dataset
**Oxford-IIIT Pet Dataset** (images only).

- ~7,400 images
- 37 different breeds
- No explicit annotations for species (cat vs dog)

Since labels are not provided directly, **class labels are inferred from file names**
based on naming conventions.

---

## Data Preparation
- Images are manually split into training and validation sets
- Custom folder structure is created:

train/
├── cats/
└── dogs/
validation/
├── cats/
└── dogs/

- Images are resized to **150×150**
- Pixel values are rescaled to [0,1]

---

## Model Architecture
A simple CNN trained from scratch:

- Conv2D + MaxPooling
- Flatten
- Dense hidden layer
- Sigmoid output for binary classification

Loss function:
- Binary Cross-Entropy

Optimizer:
- Adam

---

## Training Results
- Training accuracy approaches **~100%**
- Validation accuracy stabilizes around **~74%**
- Validation loss increases over epochs, indicating **overfitting**

This behavior is expected given:
- a relatively small dataset,
- a simple model without regularization,
- lack of data augmentation.

---

## Evaluation and Observations
- The model performs significantly better on dogs than cats
- Manual testing confirms a bias toward predicting "dog"
- Training set is **highly imbalanced**:
- Cats: ~2,300 images
- Dogs: ~4,700 images

This imbalance likely contributes to biased predictions.

---

## Key Insights
- CNNs can easily overfit small datasets when trained from scratch
- Class imbalance strongly affects model behavior
- Accuracy alone is not sufficient to assess performance
- Proper regularization, data augmentation, or transfer learning would be required for improvement

---

## Technologies Used
- Python
- TensorFlow / Keras
- NumPy, Matplotlib
- ImageDataGenerator

---

## Conclusion
This project demonstrates a complete end-to-end workflow for image classification,
highlighting common challenges such as overfitting and class imbalance.
It serves as a baseline for more advanced approaches such as data augmentation
or transfer learning.
