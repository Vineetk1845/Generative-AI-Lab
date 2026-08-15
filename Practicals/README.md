# Image Classification using CNN and Transfer Learning

**Practical No-01**
**Course:** Generative AI Lab
**Department:** CSE (AIML), T.Y. Tech
**Institution:** MIT Academy of Engineering, Alandi, Pune

**Student:** *[Enter Your Name]*
**Student ID:** *[Enter Your ID]*
**Date of Submission:** *[Enter Date]*

## Objective

Implement an image classification pipeline using a Convolutional Neural Network (CNN): train a CNN
from scratch, fine-tune a pretrained transfer learning model (MobileNetV2), and compare the
performance of both models on the same dataset.

## Reference Paper

**Pre-trained deep learning models for brain MRI image classification**
Krishnapriya & Karuna, *Frontiers in Human Neuroscience*, 2023.
[DOI: 10.3389/fnhum.2023.1150120](https://doi.org/10.3389/fnhum.2023.1150120)

The paper fine-tuned four pretrained ImageNet backbones (VGG-19, VGG-16, ResNet50, Inception V3)
on a small brain-tumor MRI dataset, finding VGG-19 performed best (99.48% accuracy). See the
notebook's "Research Paper Summary" section for full details. This project follows the same
general idea — comparing a from-scratch model against a pretrained/fine-tuned one on the same data
— applied to a general-purpose image classification benchmark.

## Dataset

**CIFAR-10** (`tf.keras.datasets.cifar10`) — 60,000 32x32 color images across 10 classes. Loads
automatically, no manual download required. A 5,000/1,000 train/test subset is used by default to
keep training time reasonable; the full dataset can be enabled in the notebook.

## Models Compared

| Model | Description |
|---|---|
| CNN From Scratch | 3 conv blocks (Conv2D + BatchNorm + MaxPool), randomly initialized, trained end-to-end |
| MobileNetV2 (Transfer Learning) | ImageNet-pretrained backbone, frozen head training followed by fine-tuning of top layers |

## How to Run

1. Open `Practical_Assignment_1_CNN_TransferLearning.ipynb` in Google Colab.
2. `Runtime > Change runtime type > GPU` (T4 or better recommended).
3. `Runtime > Run all`. Expect ~15–25 minutes total runtime.

## Results

*(Fill in after running: test accuracy and loss for both models, from the notebook's Task 3
output.)*

| Model | Test Accuracy | Test Loss |
|---|---|---|
| CNN From Scratch | | |
| MobileNetV2 (Transfer Learning) | | |

See `/screenshots` for training curves, confusion matrices, and the model comparison chart.

## Repository Contents

- `Practical_Assignment_1_CNN_TransferLearning.ipynb` — full notebook (paper summary, both models, evaluation, comparison)
- `screenshots/` — performance metric screenshots
- `README.md` — this file

## Declaration

I confirm that the work in this repository is my own and was completed following academic
integrity guidelines.
