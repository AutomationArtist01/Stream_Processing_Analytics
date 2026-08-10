# Experiment 6: One-Pass Stream Processing

## Overview

This experiment demonstrates one-pass stream processing using Python. Each value of the stream is read exactly once, the count, running sum and running average are updated immediately on arrival, and the final summary is displayed along with the execution time measured using the time module.

## Project Structure

```text
Experiment_06/
│── Experiment_06.ipynb
│── Experiment_06_Report.pdf
└── README.md
```

## Technologies Used

- Python 3.x
- Time module
- Jupyter Notebook

## Dataset

No external dataset is required. The stream is defined inside the program.

```python
stream_data = [5, 9, 11, 12, 15]
```

| Value received | Running sum | Running average |
|---------------:|------------:|----------------:|
| 5 | 5 | 5.0 |
| 9 | 14 | 7.0 |
| 11 | 25 | 8.333333333333334 |
| 12 | 37 | 9.25 |
| 15 | 52 | 10.4 |

## Features

- Reads each stream value exactly once
- Maintains a running count and running sum
- Calculates the running average after every arrival
- Stores no historical data, only summary variables
- Measures the execution time of the stream
- Displays the total elements processed, final sum and final average

## How to Run

1. Install Python 3.x.
2. Open `Experiment_06.ipynb` in Jupyter Notebook.
3. Run all cells in order.

No external libraries are required, as the time module is part of the Python standard library.

## Expected Output

The notebook displays:

- The received value, running sum and running average for each element
- Total elements processed: 5
- Final sum: 52
- Final average: 10.4
- Execution time in seconds

## Files Included

| File | Description |
|------|-------------|
| `Experiment_06.ipynb` | Jupyter Notebook containing the experiment |
| `Experiment_06_Report.pdf` | Detailed experiment report |
| `README.md` | Project documentation |

## Author

Gurrala Rohith Kumar
