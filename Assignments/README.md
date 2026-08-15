# Practice Lab Assignment 1 – Neural Network Implementation from Scratch

**Course:** `Generative AI Lab`

**Department:** `CSE (AIML)` | **Class:** `T.Y. Tech`

**Student:** `Vineet Kaldate`

**PRN:** `202401110074`

**Batch:** `A3`

**Date:** `15/08/26`

---
## Objective

Implemented a simple **feedforward neural network from scratch using Python and NumPy** without using TensorFlow, PyTorch, or Keras.

The implementation covers:

* Forward propagation
* ReLU and Softmax activation functions
* Categorical Cross-Entropy loss
* Backpropagation
* Gradient calculation
* Batch Gradient Descent

## Dataset

Used the **Wine Recognition Dataset**, containing **178 samples, 13 numerical features, and 3 wine cultivars**.

The dataset was loaded using `sklearn.datasets.load_wine`.

Dataset: https://archive.ics.uci.edu/ml/datasets/wine

## Data Preparation

* Explored the dataset and class distribution.
* Split the data into **80% training and 20% testing** using stratified sampling.
* Standardized the input features using `StandardScaler`.
* One-hot encoded the target classes.
* Obtained **142 training samples and 36 testing samples**.

## Neural Network

Implemented a feedforward neural network with:

* **Input layer:** 13 features
* **Hidden layer:** 16 neurons with ReLU
* **Output layer:** 3 neurons with Softmax
* **Learning rate:** 0.1
* **Epochs:** 1000
* **Weight initialization:** He initialization
* **Optimizer:** Batch Gradient Descent

The network, activation functions, loss function, forward pass, backpropagation, and parameter updates were implemented manually using NumPy.

## Training

The model was trained for **1000 epochs**.

During training, the loss decreased from **1.1117 to 0.0025**, and the training accuracy reached **100%**.

A training loss curve was generated to observe the learning process.

## Evaluation

The trained model was evaluated on the test dataset using:

* Accuracy
* Precision
* Recall
* F1-score
* Confusion Matrix

**Test Accuracy: 94.44%**

The confusion matrix and classification report were also generated to analyse the performance for each class.

## Model Comparison

For benchmarking, the from-scratch neural network was compared with a `scikit-learn` `MLPClassifier` using a comparable one-hidden-layer architecture.

| Model                       | Test Accuracy |
| --------------------------- | ------------: |
| From-Scratch Neural Network |    **94.44%** |
| Scikit-learn MLPClassifier  |    **97.22%** |

The comparison shows that the library-based model achieved slightly higher accuracy, while the from-scratch implementation provided direct understanding and control over the neural network calculations.

## Conclusion

Successfully implemented and trained a feedforward neural network from scratch using NumPy on the Wine Recognition Dataset.

The assignment helped in understanding how **forward propagation, activation functions, loss calculation, backpropagation, and gradient descent** work internally. The final model achieved **94.44% test accuracy**.
