# Image Segmentation Comparison: Semantic, Instance and Panoptic

## Project Overview
This project demonstrates and compares **three major types of image segmentation**:

- Semantic segmentation
- Instance segmentation
- Panoptic segmentation

All models are **pre-trained state-of-the-art architectures** and are applied to the same image
to highlight conceptual and practical differences between the approaches.

---

## Segmentation Types

### Semantic Segmentation
- Assigns a **class label to each pixel**
- Does not distinguish between different instances of the same class

**Model used:**
- SegFormer (ADE20K fine-tuned)

---

### Instance Segmentation
- Detects and segments **individual object instances**
- Multiple objects of the same class are separated

**Model used:**
- Mask R-CNN (ResNet50-FPN, COCO pre-trained)

---

### Panoptic Segmentation
- Combines **semantic and instance segmentation**
- Distinguishes:
  - *Things* (countable objects like people)
  - *Stuff* (amorphous regions like sky, water, sand)

**Model used:**
- Mask2Former (COCO Panoptic)

---

## Workflow
1. Load a single RGB image
2. Apply:
   - Semantic segmentation
   - Instance segmentation
   - Panoptic segmentation
3. Visualize and compare segmentation masks
4. Extract and analyze detected classes and instances

---

## Results
- Semantic segmentation identifies scene elements such as:
  - water, sea, sand, tree, mountain, person
- Instance segmentation correctly detects **individual people**
- Panoptic segmentation:
  - Separates background regions (*stuff*)
  - Counts object instances (*things*)

This comparison highlights the strengths and limitations of each approach.

---

## Key Insights
- Semantic segmentation is ideal for scene understanding
- Instance segmentation is best for object-level analysis
- Panoptic segmentation provides the most complete representation
- Pre-trained models can achieve strong results without fine-tuning

---

## Technologies Used
- Python
- PyTorch
- Torchvision
- HuggingFace Transformers
- NumPy, Matplotlib, PIL

---

## Conclusion
This project provides a clear and practical comparison of the main image segmentation paradigms,
demonstrating how different models and tasks address complementary aspects of visual understanding.
