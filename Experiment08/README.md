# Experiment 8: Statistical Analysis of Data using Sliding Window

## Overview

This experiment implements the sliding window algorithm for statistical analysis of a continuously arriving data stream. A window of fixed size moves across the stream one position at a time, and the mean, median, variance, standard deviation, maximum, minimum and range are recalculated for each window.

## Project Structure

```text
Experiment_08/
│── Experiment_08.ipynb
│── Experiment_08_Report.pdf
└── README.md
```

## Technologies Used

- Python 3.x
- Statistics module
- Random module
- Jupyter Notebook

## Dataset

No external dataset is required. The stream is generated at runtime.

```python
stream = [random.randint(10, 100) for i in range(20)]
```

| Parameter | Value |
|-----------|------:|
| Stream length (n) | 20 |
| Value range | 10 to 100 |
| Window size (w) | 5 |
| Total windows (n - w + 1) | 16 |

## Algorithm

1. Read the streaming data.
2. Fix the window size.
3. Move the window as new data enters.
4. Extract the current window.
5. Perform statistical analysis.
6. Display the result.
7. Repeat the steps.

## Features

- Generates a stream of 20 random values
- Uses a fixed window size of 5
- Slides the window forward one element at a time
- Calculates mean, median, variance, standard deviation, maximum, minimum and range
- Uses constant memory, since only the current window is processed
- Creates 16 windows in total

## How to Run

1. Install Python 3.x.
2. Open `Experiment_08.ipynb` in Jupyter Notebook.
3. Run all cells in order.

No external libraries are required, as the statistics and random modules are part of the Python standard library.

## Expected Output

The notebook displays, for each of the 16 windows:

- The window contents
- Mean, median, variance and standard deviation
- Maximum, minimum and range

The exact values change on every run because the stream is generated randomly.

## Files Included

| File | Description |
|------|-------------|
| `Experiment_08.ipynb` | Jupyter Notebook containing the experiment |
| `Experiment_08_Report.pdf` | Detailed experiment report |
| `README.md` | Project documentation |

## Author

Gurrala Rohith Kumar
