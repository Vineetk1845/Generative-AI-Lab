# Practical No. 01 – Image Classification using CNN and Transfer Learning

**Course:** `Generative AI Lab`

**Department:** `CSE (AIML)` | **Class:** `T.Y. Tech`

**Student:** `Vineet Kaldate`  

**PRN:** `202401110074`  

**Date:** `15/08/26`  

**Group Members:** `Rameshwar Sanap`, `Sameer Sirsath`


## Objective

Implemented an image classification pipeline using two different approaches:

- CNN trained from scratch
- Transfer learning using a pretrained MobileNetV2 model

The performance of both models was evaluated and compared on the same dataset.

## Dataset

Used the **CIFAR-10 dataset**, which contains 60,000 color images belonging to 10 classes.

The classes include:

- Airplane
- Automobile
- Bird
- Cat
- Deer
- Dog
- Frog
- Horse
- Ship
- Truck

For this implementation, a subset of the dataset was used to keep the training process manageable in Google Colab.

- Training images used: 5,000
- Testing images used: 1,000
- Training split: 4,500 images
- Validation split: 500 images
- Image size: 32 × 32 × 3

The images were normalized, class labels were one-hot encoded, and data augmentation was applied during training. :contentReference[oaicite:1]{index=1}

Dataset: https://www.cs.toronto.edu/~kriz/cifar.html

## Model 1: CNN From Scratch

A custom CNN was built and trained from randomly initialized weights.

The architecture consists of:

- 3 convolutional blocks
- Batch Normalization
- Max Pooling
- Dense layer with 128 neurons
- Dropout
- Softmax output layer with 10 classes

Data augmentation using random flipping, rotation, and zoom was also applied during training.

The model was trained using the Adam optimizer with categorical cross-entropy loss and a batch size of 32. Early stopping and learning-rate reduction were used during training. :contentReference[oaicite:2]{index=2}

## Model 2: Transfer Learning with MobileNetV2

A pretrained **MobileNetV2** model with ImageNet weights was used for transfer learning.

The CIFAR-10 images were resized from 32 × 32 to 96 × 96 and processed using the MobileNetV2 preprocessing function.

The model was trained in two stages:

1. The pretrained MobileNetV2 base was initially frozen and a new classification head was trained.
2. The top approximately 30 layers of MobileNetV2 were then unfrozen and fine-tuned using a lower learning rate.

This allowed the pretrained model to adapt its learned features to the CIFAR-10 classification task. :contentReference[oaicite:3]{index=3} :contentReference[oaicite:4]{index=4}

## Model Evaluation

Both models were evaluated on the same 1,000-image test set using:

- Test accuracy
- Test loss
- Precision
- Recall
- F1-score
- Confusion matrix

### Results

| Model | Test Accuracy | Test Loss |
|---|---:|---:|
| CNN From Scratch | **57.50%** | 1.2577 |
| MobileNetV2 Transfer Learning | **80.80%** | 0.5903 |

The MobileNetV2 transfer learning model performed significantly better than the CNN trained from scratch. :contentReference[oaicite:5]{index=5}

## Classification Performance

The MobileNetV2 model achieved an overall accuracy of approximately **81%**, while the CNN from scratch achieved approximately **57%** on the test set.

The classification reports were generated for all 10 CIFAR-10 classes, along with confusion matrices for both models. :contentReference[oaicite:6]{index=6}

## Comparison with Reference Paper

The reference research paper studied pretrained CNN models for brain MRI image classification and reported strong performance from transfer learning models.

In this practical, the same general idea was explored using **CIFAR-10** instead of brain MRI images and **MobileNetV2** instead of the architectures used in the paper.

The results from this implementation also show the advantage of transfer learning: MobileNetV2 achieved **80.80%**, compared with **57.50%** from the CNN trained from scratch.

## Visualizations

The implementation includes:

- Sample CIFAR-10 images
- Training accuracy and loss curves
- Confusion matrices for both models
- Model accuracy comparison chart

## Conclusion

A CNN was successfully implemented and trained from scratch, and a pretrained MobileNetV2 model was fine-tuned using transfer learning on the CIFAR-10 dataset.

The CNN from scratch achieved **57.50% test accuracy**, while the MobileNetV2 transfer learning model achieved **80.80%**.

The comparison demonstrates that using a pretrained model can provide better performance than training a CNN from random initialization, particularly when working with a relatively small training subset.

## Declaration

I, **Vineet Kaldate**, confirm that the work submitted in this assignment is my own and has been completed following academic integrity guidelines.

**GitHub Repository:** https://github.com/Vineetk1845/Generative-AI-Lab

**Signature:** Vineet Manohar Kaldate
