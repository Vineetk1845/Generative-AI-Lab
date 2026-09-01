# Practical No-01: Image Classification using CNN and Transfer Learning

**Course:** Generative AI LAB

**Group Members:** `Rameshwar Sanap`, `Sameer Sirsath`, `Vineet Kaldate`

**Environment:** PyCharm Notebook / Jupyter (`.ipynb`)

**Target Hardware:** NVIDIA GeForce RTX 3050 (6GB VRAM)

---

## Overview

This project benchmarks a **Custom CNN** (trained from scratch) against three **pre-trained transfer-learning backbones** — **VGG16**, **MobileNetV2**, and **EfficientNetB0** — on a 3-class rice leaf disease image classification task:

- `Bacterial_Blight`
- `Brown_Spot`
- `Leaf_Smut`

The notebook automatically looks for a local dataset (`dataset_raw`, `rice_leaf_diseases`, `kaggle_dataset`, or `rice_leaf`) and organizes it into `train/val/test` splits (80/10/10). If no dataset is found, it falls back to generating **synthetic leaf images** so the pipeline can still run end-to-end for demonstration purposes.

## Features

- PyTorch 2.x training pipeline with **Automatic Mixed Precision (AMP)** via `torch.amp.autocast` and `torch.amp.GradScaler`
- Data augmentation: random resized crop, horizontal flip, rotation, color jitter, and ImageNet normalization
- Four model architectures compared side by side:
  - **Custom CNN** — 4-block `[Conv2D → BatchNorm → ReLU → MaxPool2D]` architecture with Global Average Pooling (~423K parameters)
  - **VGG16** — pre-trained, frozen convolutional features, custom classifier head
  - **MobileNetV2** — pre-trained, frozen convolutional features, custom classifier head
  - **EfficientNetB0** — pre-trained, frozen convolutional features, custom classifier head
- Feature map visualization using PyTorch forward hooks (early / middle / deep convolutional layers)
- Full evaluation suite: **Accuracy, Precision, Recall, F1-Score (macro), ROC-AUC, Confusion Matrix**
- Comparative visualizations: accuracy/latency bar charts, confusion matrix grids, training/validation loss & accuracy curves
- Single-image inference demo (ground truth vs. predicted class with confidence score)

## Repository Structure

```
.
├── Practical_No-01_Image_Classification_using_CNN_and_Transfer_Learning.ipynb
└── README.md
```

## Requirements

- Python 3.9+
- PyTorch 2.x with CUDA support (recommended; CPU also works but is slower)
- Install dependencies:

```bash
pip install torch torchvision numpy pandas matplotlib seaborn pillow scikit-learn
```

## Dataset Setup

Place a raw dataset folder in the project root using one of the following names, with subfolders named exactly as below:

```
dataset_raw/
├── Bacterial leaf blight/
├── Brown spot/
└── Leaf smut/
```

The notebook will automatically split this into `dataset/train`, `dataset/val`, and `dataset/test` (80/10/10) with `250` samples per class by default. If no such folder is found, synthetic leaf images are generated instead so the notebook can still run.

## How to Run

1. Clone the repository and install the requirements above.
2. (Optional) Add your dataset as described in [Dataset Setup](#dataset-setup).
3. Open the notebook:

```bash
jupyter notebook Practical_No-01_Image_Classification_using_CNN_and_Transfer_Learning.ipynb
```

4. Run all cells sequentially. The notebook will:
   - Set seeds and detect GPU/CPU
   - Prepare the dataset (real or synthetic)
   - Build DataLoaders with augmentations
   - Define and train all four models (5 epochs each by default)
   - Visualize intermediate feature maps
   - Evaluate all models on the test set
   - Generate comparison tables, charts, and confusion matrices
   - Run single-image inference

## Results Summary

The notebook produces a comparative table across models with the following metrics:

| Metric | Description |
|---|---|
| Accuracy (%) | Overall test-set classification accuracy |
| Precision (Macro) | Macro-averaged precision across classes |
| Recall (Macro) | Macro-averaged recall across classes |
| F1-Score (Macro) | Macro-averaged F1-score across classes |
| ROC-AUC | Multi-class ROC-AUC score |
| Training Time | Wall-clock training time per model |
| Parameters | Total and trainable parameter counts |

**Key findings:**
- Pre-trained backbones (VGG16, MobileNetV2, EfficientNetB0) generally achieve stronger accuracy thanks to ImageNet-pretrained representations.
- The Custom CNN achieves competitive accuracy with a fraction of the parameters (~423K vs. VGG16's ~134M), making it attractive for resource-constrained deployment.

## Academic Context

This experiment is inspired by comparative research on CNN vs. transfer-learning approaches for plant disease classification (referenced paper: arXiv:2601.02246) and evaluates trade-offs between training-from-scratch and fine-tuning pre-trained architectures.

## Declaration

This project was submitted as part of the Generative AI LAB course by group members Rameshwar Sanap, Sameer Sirsath, and Vineet Kaldate as an original implementation.
