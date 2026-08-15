# Neural Network Implementation from Scratch

**Course:** Generative AI Lab
**Department:** CSE (AIML), T.Y. Tech
**Institution:** MIT Academy of Engineering, Alandi, Pune

**Student:** Atharva Kadam
**PRN:** 202401110067
**Batch:** A1
**Date of Submission:** 15th August 2026

## 1. Objective

The objective of this assignment is to implement a simple feedforward neural network from scratch using Python. The implementation covers the major steps involved in training a neural network, including the forward pass, backpropagation, and weight updates using gradient descent.

The neural network is implemented without using deep learning frameworks such as TensorFlow, PyTorch, or Keras.

## 2. Dataset

The **Wine Recognition Dataset** from `sklearn.datasets.load_wine` is used for this assignment.

* **Number of samples:** 178
* **Number of features:** 13
* **Number of classes:** 3
* **Task:** Multi-class classification

Scikit-learn is used for loading, splitting, and scaling the dataset, as well as for evaluating the final model. The neural network itself is implemented manually.

## 3. Model Architecture

| Layer        | Neurons | Activation |
| ------------ | ------: | ---------- |
| Input Layer  |      13 | —          |
| Hidden Layer |      16 | ReLU       |
| Output Layer |       3 | Softmax    |

**Training components:**

* **Loss Function:** Categorical Cross-Entropy
* **Optimizer:** Batch Gradient Descent
* **Weight Initialization:** He Initialization
* **Backpropagation:** Manually implemented

## 4. Implementation

The notebook contains the complete implementation of the neural network, including:

* Dataset loading and preprocessing
* Feature scaling
* Weight and bias initialization
* Forward propagation
* ReLU activation
* Softmax activation
* Categorical cross-entropy loss
* Backpropagation
* Gradient calculation
* Weight and bias updates
* Model training
* Performance evaluation

## 5. Results

The implemented neural network achieved:

**Test Accuracy: 94.44%**

For comparison, the model was also compared with Scikit-learn's `MLPClassifier`, which achieved **97.22%** on the same task.

The comparison and observations are included in the notebook.

## 6. Performance Analysis

The repository contains visual results from the experiment, including:

* Training loss curve
* Confusion matrix
* Classification report
* Neural network vs. `MLPClassifier` comparison

These results are available in the `screenshots/` folder.

## 7. Repository Contents

```text
├── FirstName_LastName_GenerativeAILabAssignment.ipynb
├── screenshots/
│   ├── training_loss_curve
│   ├── confusion_matrix
│   ├── classification_report
│   └── model_comparison
└── README.md
```

### Files

* **Notebook:** Contains the complete neural network implementation, training process, and results.
* **screenshots/:** Contains the important outputs and performance visualizations.
* **README.md:** Provides an overview of the assignment and its results.

## 8. Conclusion

This assignment demonstrates the basic working of a feedforward neural network by implementing its main components from scratch. The implementation provides an understanding of how forward propagation, loss calculation, backpropagation, and gradient descent work together during model training.

The model achieved a test accuracy of **94.44%** on the Wine dataset, showing that a neural network implemented from basic mathematical operations can perform effectively on a multi-class classification problem.

## 9. Declaration

I confirm that the work in this repository is my own and was completed following academic integrity guidelines.
