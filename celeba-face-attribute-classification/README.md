# Face Attribute Classification on CelebA Dataset

## Project Overview
This project focuses on **face attribute classification** using the CelebA dataset.
Both **binary classification** and **multi-label classification** tasks are explored,
leveraging convolutional neural networks and transfer learning.

The main goals are:
- to build CNN models for image-based classification,
- to analyze performance across different facial attributes,
- to study the impact of transfer learning and fine-tuning.

---

## Dataset
**CelebA Dataset** (~200,000 images of celebrity faces).

- Each image is annotated with **40 binary attributes**
- Official split provided by the authors:
  - Training
  - Validation
  - Test

In this project, the following attributes are used:
- `Male`
- `Smiling`
- `Eyeglasses`
- `Blond_Hair`
- `Young`

---

## Methods

### 1️⃣ Binary Classification
- Task: Predict the attribute **Male**
- Model: Custom CNN trained from scratch
- Input size: 150 × 150 RGB images
- Loss: Binary Cross-Entropy
- Metric: Accuracy

**Results:**
- Test accuracy ≈ **95%**
- Analysis via confusion matrix and class-wise error rates
- Higher misclassification rate observed for female class, suggesting higher visual variability

---

### 2️⃣ Multi-Label Classification
- Task: Predict multiple facial attributes simultaneously
- Model: **MobileNetV2** backbone (ImageNet pretrained)
- Output: Sigmoid-activated multi-label predictions
- Loss: Binary Cross-Entropy

**Initial Results (frozen backbone):**
- Overall accuracy ≈ **58%**
- Strong performance on individual attributes (e.g. Eyeglasses, Blond_Hair)

---

### 3️⃣ Fine-Tuning
- Unfreezing last layers of MobileNetV2
- Reduced learning rate to preserve pretrained representations

**After fine-tuning:**
- Overall accuracy increased to ≈ **70%**
- Significant improvement across all selected attributes
- Performance gain of ~**12%** compared to frozen model

---

## Key Results

| Attribute      | Accuracy (after fine-tuning) |
|----------------|------------------------------|
| Male           | ~0.95 |
| Smiling        | ~0.86 |
| Eyeglasses     | ~0.99 |
| Blond_Hair     | ~0.95 |
| Young          | ~0.86 |

Note: Overall accuracy is strict, as **all attributes must be predicted correctly at once**.

---

## Insights
- Transfer learning significantly improves performance on complex visual tasks
- Fine-tuning is crucial to adapt pretrained models to domain-specific features
- Some attributes are inherently easier to detect (e.g. Eyeglasses)
- Multi-label accuracy should be interpreted together with per-attribute metrics

---

## Technologies Used
- Python
- TensorFlow / Keras
- MobileNetV2 (transfer learning)
- NumPy, Pandas, Matplotlib
- Scikit-learn (evaluation metrics)

---

## Conclusion
This project demonstrates a complete deep learning workflow for image-based
classification, including data preprocessing, CNN design, transfer learning,
fine-tuning, and detailed performance analysis on real-world data.
