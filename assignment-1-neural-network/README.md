# Neural Network Implementation from Scratch

**Course:** Generative AI Lab
**Department:** CSE (AIML), T.Y. Tech
**Institution:** MIT Academy of Engineering, Alandi, Pune

**Student:** Atharva Kadam
**PRN:** 202401110067
**Batch:** A1
**Date of Submission:** 15th August 2026

## Objective

Implement a simple feedforward neural network **from scratch** in Python — without using any
in-built deep learning libraries (no TensorFlow, PyTorch, or Keras) — covering the forward pass,
backpropagation, and training via gradient descent.

## Dataset

**Wine recognition dataset** (`sklearn.datasets.load_wine`) — 178 samples of wine, each described
by 13 chemical-analysis features, labeled with one of 3 cultivars (grape varieties). Task: multi-class
classification.

`scikit-learn` is used only to load/split/scale the data and for evaluation metrics — **not** to build
or train the neural network itself.

## Model Architecture

| Layer | Neurons | Activation |
|---|---|---|
| Input | 13 | — |
| Hidden | 16 | ReLU |
| Output | 3 | Softmax |

- **Loss:** Categorical Cross-Entropy
- **Optimizer:** Batch Gradient Descent (manually implemented)
- **Weight init:** He initialization

## How to Run

1. Open `FirstName_LastName_GenerativeAILabAssignment.ipynb` in Google Colab or Jupyter.
2. Run all cells top to bottom (`Runtime > Run all` in Colab).
3. No external downloads needed — the dataset loads directly via `scikit-learn`.

## Results

- **Test Accuracy:** 94.44%
- Benchmarked against `scikit-learn`'s `MLPClassifier` (97.22%) for comparison — see notebook
  Part F for discussion.

See `/screenshots` for training loss curve, confusion matrix, classification report, and the
model comparison chart.

## Repository Contents

- `FirstName_LastName_GenerativeAILabAssignment.ipynb` — full notebook (implementation + results)
- `screenshots/` — performance metric screenshots
- `README.md` — this file

## Declaration

I confirm that the work in this repository is my own and was completed following academic
integrity guidelines.
