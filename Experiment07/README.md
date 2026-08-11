# Experiment 7: Case Study on Incremental Learning

## Overview

This experiment implements an incremental intrusion detection model for real-time network traffic using Stochastic Gradient Descent. An `SGDClassifier` is trained on an initial batch of data and then updated record by record using `partial_fit()` as new traffic arrives, so the model learns continuously without being retrained on the full dataset.

## Project Structure

```text
Experiment_07/
│── Experiment_07.ipynb
│── Experiment_07_Report.pdf
└── README.md
```

## Technologies Used

- Python 3.x
- NumPy
- Scikit-learn
- Jupyter Notebook

## Dataset

No external dataset is required. Synthetic network traffic is generated using NumPy.

| Stage | Samples | Features | Purpose |
|-------|--------:|---------:|---------|
| Initial training | 100 | 2 | Builds the first version of the model |
| Incoming stream | 20 | 2 | Predicted, then learned from one at a time |
| Testing | 50 | 2 | Measures final accuracy |

The class label follows the rule `y = (x1 + x2 > 0)`, where 1 represents an intrusion and 0 represents normal traffic.

## Features

- Trains an SGD classifier with `log_loss` for binary classification
- Uses `partial_fit()` to support incremental learning
- Simulates 20 new incoming records arriving one at a time
- Predicts each record before learning from it
- Updates the model after every record without full retraining
- Measures final accuracy on unseen test data

## How to Run

1. Install Python 3.x.
2. Install the required libraries.

```bash
pip install numpy scikit-learn
```

3. Open `Experiment_07.ipynb` in Jupyter Notebook.
4. Run all cells in order.

## Expected Output

The notebook displays:

- The prediction and actual label for each of the 20 incoming records
- A final test accuracy of approximately 0.98, that is 98%

The exact accuracy varies slightly between runs because the data is generated randomly.

## Discussion Questions

- **Why SGD and not a Decision Tree, Random Forest or Neural Network?** Only SGD supports `partial_fit()` for one record at a time, uses less memory and suits real-time streaming data.
- **Is a complete IDS implemented?** No. Synthetic data is used instead of real packets, so the model only simulates the detection component of an IDS.

Both questions are answered in full in the report.

## Files Included

| File | Description |
|------|-------------|
| `Experiment_07.ipynb` | Jupyter Notebook containing the experiment |
| `Experiment_07_Report.pdf` | Detailed experiment report |
| `README.md` | Project documentation |

## Author

Gurrala Rohith Kumar
