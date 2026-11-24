# IoT-Enabled Real-Time Computer Vision System for Automated Printing Defect Detection

**A Computer Vision and Deep Learning-Based Approach for Automated Printing Quality Inspection**

**Major Project | B.Tech Computer Science and Engineering**

The NorthCap University, Gurugram, India

**Project Team**
- Ananya Verma (23CSU028)
- Anisha Boken (23CSU030)

**Project Supervisors**
- Dr. Anuradha Dhull
- Dr. Shilpa Mahajan

---

## 1. Overview

This project focuses on developing a computer vision-based system for automatically detecting and localising printing defects in printed documents.

The work addresses the limitations of manual print inspection by developing a specialised 15-class printing-defect dataset and evaluating multiple YOLO-based object detection models.

The project also explores an Enhanced Siamese Network combining EfficientNet-B4 and CLIP features for additional visual feature representation.

The current research establishes the dataset and model-development foundation for a future camera-based, IoT-enabled printing inspection system.

## 2. Problem Statement

Printing defects such as smudging, missing content, faded ink, incorrect characters and misalignment can affect document readability and quality.

Manual inspection can be time-consuming and inconsistent, particularly when large volumes of printed documents need to be examined.

The project aims to develop and evaluate deep learning-based object detection models capable of identifying and localising different printing defects.

## 3. Project Objectives

- Develop a specialised dataset covering 15 printing-defect categories.
- Collect physical defective print samples and additional synthetic examples.
- Annotate defective regions using bounding boxes in Roboflow.
- Apply image preprocessing and augmentation.
- Train and compare multiple YOLO object detection configurations.
- Evaluate detection performance using precision, recall, F1-score and mAP.
- Explore additional feature representation using an Enhanced Siamese Network.
- Establish a foundation for future camera and IoT integration.

## 4. Dataset Development

The dataset was developed using physically collected defective printed samples from The NorthCap University printing facility and additional examples generated using Claude.

| Dataset Metric | Original Dataset | Roboflow V3 |
|---|---:|---:|
| Images | 2,435 | 5,845 |
| Bounding-box annotations | 9,374 | 15,729 |
| Defect categories | 15 | 15 |

### Dataset Distribution

**Original dataset**
- Training: 1,705 images
- Validation: 487 images
- Testing: 243 images

**Roboflow V3**
- Training: 5,115 images
- Validation: 487 images
- Testing: 243 images

### Fifteen Printing-Defect Categories

1. faded_print
2. wrong_font
3. colour_difference
4. incorrect_size
5. missing_section
6. smudges
7. uneven_ink_density
8. double_printing
9. ink_spots_on_paper
10. tears_wrinkles_folds
11. misalignment
12. cropped_image
13. missing_print
14. broken_extra_wrong_characters
15. random_black_white_lines

## 5. Data Annotation and Preprocessing

The dataset was reviewed and annotated using Roboflow.

The preprocessing pipeline included:

- Bounding-box annotation and class labelling.
- Image resizing to 512 × 512 pixels.
- Random cropping.
- Rotation.
- Brightness and exposure adjustments.
- Gaussian blur augmentation.
- Export in YOLO-compatible format.

## 6. Model Development and Experiments

Three experimental phases were conducted to study different dataset versions and training configurations.

### Phase 1 – Initial Baseline

Models evaluated:
- YOLOv5s
- YOLOv8s
- YOLO11s
- YOLO26n

Best mAP@0.5: 0.4630 – YOLOv8s

### Phase 2 – Augmented Dataset

Models evaluated:
- YOLOv5s
- YOLOv8s
- YOLO11s
- YOLO26n

Best mAP@0.5: 0.3535 – YOLOv8s

### Phase 3 – Final Model Comparison

Models evaluated:
- YOLOv5s-U
- YOLOv8s
- YOLO11s

| Model | Precision | Recall | mAP@0.5 | mAP@0.5:0.95 | F1 |
|---|---:|---:|---:|---:|---:|
| YOLOv5s-U | 0.4807 | 0.4383 | 0.4019 | 0.2303 | 0.4586 |
| YOLOv8s | 0.4752 | 0.4162 | 0.3843 | 0.2377 | 0.4437 |
| YOLO11s | 0.5143 | 0.4365 | 0.4335 | 0.2617 | 0.4722 |

**Best Phase 3 mAP@0.5: YOLO11s – 0.4335**

The Phase 3 test set contained 243 images and 698 annotated instances.

## 7. Additional Feature-Representation Experiment

An Enhanced Siamese Network experiment was conducted using:

- EfficientNet-B4 feature extraction.
- CLIP ViT-B/32 image embeddings.
- Feature fusion and projection.
- Transformer encoder.
- Class-aware proxy triplet training.

The network was trained for 10 epochs.

The experiment showed a reduction in training loss. Further evaluation using verified matching pairs is required before establishing its effectiveness for print similarity verification.

## 8. Technology and Tools

- Python
- YOLO object detection models
- Ultralytics
- Roboflow
- EfficientNet-B4
- CLIP ViT-B/32
- Enhanced Siamese Network
- Deep Learning and Computer Vision

## 9. Current Development Status

**Completed research and implementation work**
- Dataset development and curation.
- Fifteen-class defect taxonomy.
- Image annotation and preprocessing.
- Dataset augmentation and YOLO export.
- Three phases of YOLO model experiments.
- Model comparison and performance evaluation.
- Class-wise error analysis.
- Exploratory Enhanced Siamese Network experiment.

**Planned development**
- Camera-based sample acquisition.
- Expansion of physical defect samples.
- Repeated experiments using multiple random seeds.
- Improvements for difficult defect categories.
- Camera integration and IoT communication.
- Edge-device deployment and real-time inspection.

## 10. Limitations

- Some defect categories remain difficult to detect.
- Current evaluation uses a test set of 243 images.
- Experiments use a single random seed.
- The final camera-based acquisition and IoT deployment have not yet been implemented.

## 11. Future Scope

- Real-time defect detection using camera-based image acquisition.
- Integration with IoT-enabled monitoring.
- Edge deployment for industrial inspection.
- Improved detection of subtle and small defects.
- Expanded physical dataset and additional evaluation.

## 12. Repository Structure

The repository will contain source code, dataset documentation, experiment configurations, evaluation results, diagrams and project documentation.

## 13. Academic Information

**Project:** Major Project, B.Tech CSE

**Institution:** The NorthCap University, Gurugram

**Academic Session:** 2026–2027

---

*This repository documents the development, experimentation and research progress of the printing defect detection project. It will be updated as additional implementation and evaluation work is completed.*
