# Experiment 11: Implementation of the VFDT Algorithm for Data Classification

## Overview

This experiment implements the Very Fast Decision Tree (VFDT), also known as the Hoeffding Tree, from scratch in Python. The tree is built incrementally from a data stream: each example is read once, used to update the statistics stored at a leaf, and then discarded. The Hoeffding bound decides when a leaf has seen enough examples to split confidently.

## Project Structure

```text
Experiment_11/
│── Experiment_11.ipynb
│── Experiment_11_Report.pdf
└── README.md
```

## Technologies Used

- Python 3.x
- NumPy
- Scikit-learn
- Jupyter Notebook

## Hoeffding Bound

```text
epsilon = sqrt( (R^2 * ln(1 / delta)) / (2 * n) )
```

A leaf splits when the information gain of the best attribute exceeds that of the second best attribute by more than `epsilon`.

## Dataset

No external dataset is required. The data is generated with `make_classification`.

| Parameter | Value |
|-----------|------:|
| Samples | 1000 |
| Features | 4 |
| Informative features | 4 |
| Redundant features | 0 |
| random_state | 42 |
| Train / test split | 70% / 30% |
| delta | 0.01 |
| min_samples | 40 |

Continuous features are rounded with `np.round()` so the tree can split on discrete values.

## Implementation Steps

1. Library
2. VFDT Node
3. VFDT Tree
4. Entropy
5. Hoeffding bound
6. Predict
7. Dataset
8. Discretize
9. Accuracy calculation

## Features

- Builds the decision tree incrementally, one example at a time
- Stores only class and feature counts at each leaf, never the examples
- Calculates entropy and information gain from the stored counts
- Applies the Hoeffding bound to decide when a split is statistically safe
- Splits a leaf only after it has seen at least 40 samples
- Predicts by walking the tree and returning the majority class of the leaf reached

## How to Run

1. Install Python 3.x.
2. Install the required libraries.

```bash
pip install numpy scikit-learn
```

3. Open `Experiment_11.ipynb` in Jupyter Notebook.
4. Run all cells in order.

## Expected Output

```text
Dataset shape : (1000, 4)
Training samples : 700
Testing samples  : 300
Root split feature : 1
Number of children : 10
Accuracy = 0.76
```

## Files Included

| File | Description |
|------|-------------|
| `Experiment_11.ipynb` | Jupyter Notebook containing the experiment |
| `Experiment_11_Report.pdf` | Detailed experiment report |
| `README.md` | Project documentation |

## Author

Gurrala Rohith Kumar
