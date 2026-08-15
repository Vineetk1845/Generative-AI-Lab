# Practice Lab Assignment 1 – Neural Network Implementation from Scratch

**Course:** Generative AI Lab

**Department:** CSE (AIML) | **Class:** T.Y. Tech

**Institution:** MIT Academy of Engineering, Alandi, Pune

**Student Name:** Vineet Kaldate

**PRN Number:** 202401110074

**Batch:** A3

**Date of Submission:** 15/08/26

---

## 1. Objective

The objective of this assignment is to implement a simple **feedforward neural network from scratch** using Python and NumPy.

The implementation covers the main components of a neural network:

* Forward pass
* Activation functions
* Categorical cross-entropy loss
* Backpropagation
* Gradient calculation
* Training using batch gradient descent

No deep learning frameworks such as TensorFlow, PyTorch, or Keras are used for the neural network implementation. Scikit-learn is used for loading the dataset, splitting and scaling the data, evaluation metrics, and benchmarking against an alternative model.

---

## 2. Dataset

The **Wine Recognition Dataset** is used for the classification task.

**Dataset Source:** [UCI Machine Learning Repository – Wine Dataset](https://archive.ics.uci.edu/ml/datasets/wine)

The dataset contains:

* **178 samples**
* **13 numerical features**
* **3 classes/cultivars**

The 13 features describe different chemical properties of the wine, including alcohol, malic acid, magnesium, flavanoids, color intensity, hue, and proline.

The task is to predict which of the three wine cultivars a sample belongs to based on its chemical-analysis features.

---

## 3. Data Preparation

The dataset was loaded using `sklearn.datasets.load_wine`.

The following preprocessing steps were performed:

* Dataset exploration and basic analysis
* 80/20 train-test split
* Stratified splitting to preserve class proportions
* Feature standardization using `StandardScaler`
* One-hot encoding of the target classes

The resulting dataset contains:

* **Training samples:** 142
* **Testing samples:** 36

---

## 4. Neural Network Architecture

A single-hidden-layer feedforward neural network was implemented.

| Layer        | Neurons | Activation |
| ------------ | ------: | ---------- |
| Input Layer  |      13 | —          |
| Hidden Layer |      16 | ReLU       |
| Output Layer |       3 | Softmax    |

### Training Configuration

* **Loss Function:** Categorical Cross-Entropy
* **Optimizer:** Batch Gradient Descent
* **Learning Rate:** 0.1
* **Epochs:** 1000
* **Weight Initialization:** He Initialization

---

## 5. Implementation From Scratch

The neural network was implemented using **NumPy** without using a deep learning framework.

The implementation includes:

### Activation Functions

* ReLU
* ReLU derivative
* Softmax

### Neural Network Operations

* Weight and bias initialization
* Forward propagation
* Cross-entropy loss calculation
* Backpropagation
* Gradient calculation
* Gradient-descent parameter updates
* Prediction

The `NeuralNetwork` class contains the complete implementation of these operations.

---

## 6. Training

The network was trained for **1000 epochs** using full-batch gradient descent.

During training, the loss decreased from **1.1117** at the beginning to **0.0025** by the final epoch.

The training accuracy reached **100%** during training.

A training-loss curve was generated to visualize the change in loss over the training epochs.

---

## 7. Model Evaluation

The trained network was evaluated on the held-out test set using:

* Accuracy
* Precision
* Recall
* F1-score
* Confusion Matrix

### Test Accuracy

**94.44%**

### Classification Performance

| Class   | Precision | Recall | F1-Score |
| ------- | --------: | -----: | -------: |
| Class 0 |      1.00 |   1.00 |     1.00 |
| Class 1 |      0.88 |   1.00 |     0.93 |
| Class 2 |      1.00 |   0.80 |     0.89 |

**Overall Accuracy:** 94.44%

---

## 8. Confusion Matrix

The confusion matrix obtained on the test set was:

|                | Predicted Class 0 | Predicted Class 1 | Predicted Class 2 |
| -------------- | ----------------: | ----------------: | ----------------: |
| Actual Class 0 |                12 |                 0 |                 0 |
| Actual Class 1 |                 0 |                14 |                 0 |
| Actual Class 2 |                 0 |                 2 |                 8 |

The model correctly classified all Class 0 and Class 1 samples. Two Class 2 samples were incorrectly classified as Class 1.

---

## 9. Comparison with Scikit-learn MLP

For benchmarking purposes, the from-scratch neural network was compared with a comparable `scikit-learn` `MLPClassifier` having one hidden layer with 16 neurons.

| Model                       | Test Accuracy |
| --------------------------- | ------------: |
| From-Scratch Neural Network |    **94.44%** |
| Scikit-learn MLPClassifier  |    **97.22%** |

The library-based model achieved slightly higher accuracy. However, the from-scratch implementation provides direct understanding and control over the mathematical operations involved in neural network training.

---

## 10. Observations

* The Wine dataset can be classified effectively using a relatively simple neural network.
* Feature standardization is important because the input features have different numerical scales.
* The from-scratch implementation successfully performs forward propagation, loss calculation, backpropagation, and parameter updates.
* The from-scratch model achieved **94.44% test accuracy**.
* The `MLPClassifier` achieved **97.22%**, providing a useful benchmark.
* The from-scratch implementation provides more transparency into the internal calculations of a neural network.
* Plain batch gradient descent does not include techniques such as adaptive learning rates, momentum, or regularization.

---

## 11. Visualizations

The assignment includes the following visual outputs:

* Training loss curve
* Confusion matrix
* Model accuracy comparison chart

These visualizations help analyse the training process and compare the performance of the two models.

---

## 12. Conclusion

A feedforward neural network was successfully implemented from scratch using NumPy and trained on the Wine Recognition Dataset.

The implementation covered the complete basic training process, including forward propagation, categorical cross-entropy loss, backpropagation, and gradient-descent-based parameter updates.

The model achieved a **94.44% test accuracy**, while the comparable scikit-learn MLP achieved **97.22%**. The experiment demonstrates how the fundamental mathematical operations of a neural network can be implemented and understood without relying on deep learning frameworks.

---

## 13. Repository Contents

```text
├── FirstName_LastName_GenerativeAILabAssignment.ipynb
├── screenshots/
│   ├── training_loss.png
│   ├── confusion_matrix.png
│   └── model_comparison.png
└── README.md
```

* **Jupyter Notebook:** Complete implementation, training, evaluation, and analysis.
* **screenshots/:** Important output visualizations and performance results.
* **README.md:** Overview of the assignment, methodology, and results.

---

## 14. Declaration

I, **Vineet Kaldate**, confirm that the work submitted in this assignment is my own and has been completed following academic integrity guidelines.

**GitHub Repository:** https://github.com/Vineetk1845/Generative-AI-Lab

**Signature:** Vineet Manohar Kaldate
