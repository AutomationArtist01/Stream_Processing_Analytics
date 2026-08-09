# Experiment 3: Concept Drift Detection

## Overview

This experiment demonstrates concept drift using Python and Scikit-learn. A Logistic Regression model is trained on a dataset generated from one target rule. A new dataset is then generated with a changed target rule, the old model is evaluated on it, and the accuracy before and after the drift is compared and visualized.

## Project Structure

```text
Experiment_03/
│── Experiment_03.ipynb
│── Experiment_03_Report.pdf
└── README.md
```

## Technologies Used

- Python 3.x
- NumPy
- Pandas
- Matplotlib
- Scikit-learn
- Jupyter Notebook

## Dataset

The dataset is generated synthetically using NumPy.

| Stage | Samples | Features | Target Rule |
|-------|--------:|---------:|-------------|
| Before drift | 1000 | 2 | `y = (x1 + x2 > 0)` |
| After drift | 1000 | 2 | `y = (x1 - x2 > 0)` |

## Features

- Generates a synthetic dataset before drift
- Splits the data into 70% training and 30% testing
- Trains a Logistic Regression model
- Measures accuracy before drift
- Generates a new dataset with a changed target rule
- Measures accuracy of the old model after drift
- Compares both accuracies with a bar chart

## How to Run

1. Install Python 3.x.
2. Install the required libraries.

```bash
pip install numpy pandas matplotlib scikit-learn
```

3. Open `Experiment_03.ipynb` in Jupyter Notebook.
4. Run all cells in order.

## Expected Output

The notebook displays:

- Accuracy before drift (approximately 0.99)
- Accuracy after drift (approximately 0.52)
- A performance comparison printout
- A bar chart with a clearly lower second bar

## Files Included

| File | Description |
|------|-------------|
| `Experiment_03.ipynb` | Jupyter Notebook containing the experiment |
| `Experiment_03_Report.pdf` | Detailed experiment report |
| `README.md` | Project documentation |

## Author

Gurrala Rohith Kumar
