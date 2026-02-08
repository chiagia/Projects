# Flower Image Classification with CNN and Data Augmentation

## Project Overview
This project focuses on **multi-class image classification** using a Convolutional Neural Network
trained from scratch. The task is to classify flower images into five different categories.

The main objective is to analyze **overfitting** and demonstrate how **data augmentation**
can significantly improve model generalization.

---

## Dataset
**TensorFlow Flower Dataset**

- 3,670 images
- 5 classes:
  - daisy
  - dandelion
  - roses
  - sunflowers
  - tulips

Images vary in size and orientation and are resized to a fixed resolution before training.

---

## Data Preparation
- Images resized to **180×180**
- Pixel values rescaled to [0,1]
- Train/Test split:
  - 90% training
  - 10% testing

Labels are encoded as integers and handled using sparse categorical cross-entropy.

---

## Model Architecture
A CNN trained from scratch with:

- 3 convolutional blocks (Conv2D + MaxPooling)
- Fully connected layers
- Softmax-style logits output for multi-class classification

Loss function:
- Sparse Categorical Cross-Entropy

Optimizer:
- Adam

---

## Baseline Results (No Augmentation)
- Training accuracy reaches **~100%**
- Test accuracy drops to **~61%**

This large gap clearly indicates **severe overfitting**.

---

## Data Augmentation
To improve generalization, the following augmentation techniques are applied during training:

- Random horizontal flipping
- Random rotation
- Random zoom
- Dropout layer for regularization

Augmentation is applied **only to the training data**.

---

## Results with Data Augmentation
- Test accuracy improves from **~61% to ~75%**
- Training accuracy increases more gradually
- Reduced overfitting and improved generalization

This demonstrates the effectiveness of data augmentation when training CNNs on limited datasets.

---

## Key Insights
- CNNs trained from scratch easily overfit small image datasets
- Validation/test accuracy is more informative than training accuracy
- Data augmentation acts as an implicit regularizer
- Improving generalization is often more important than increasing model complexity

---

## Technologies Used
- Python
- TensorFlow / Keras
- OpenCV
- NumPy, Matplotlib

---

## Conclusion
This project highlights a common challenge in deep learning—overfitting—and shows
how data augmentation can significantly improve model performance.
It provides a strong baseline for further improvements such as transfer learning.
