# Experiment 5: Count Number of Occurrences in a Data Stream

## Overview

This experiment demonstrates single pass frequency counting on a data stream using Python. Elements arrive one after another, a dictionary is updated immediately as each element is read, and the final frequency of every element is displayed without scanning the stream a second time.

## Project Structure

```text
Experiment_05/
│── Experiment_05.ipynb
│── Experiment_05_Report.pdf
└── README.md
```

## Technologies Used

- Python 3.x
- Jupyter Notebook

## Dataset

No external dataset is required. The stream is defined inside the program.

```python
stream = ['A', 'B', 'C', 'D', 'A', 'B', 'C', 'D', 'E', 'A']
```

| Element | Occurrences |
|---------|------------:|
| A | 3 |
| B | 2 |
| C | 2 |
| D | 2 |
| E | 1 |

## Features

- Defines a data stream of 10 elements
- Uses a dictionary as the counter
- Processes every element in a single pass
- Prints the running count after each arrival
- Displays a final frequency summary
- Requires no second scan of the stream

## How to Run

1. Install Python 3.x.
2. Open `Experiment_05.ipynb` in Jupyter Notebook.
3. Run all cells in order.

No external libraries are required.

## Expected Output

The notebook displays:

- The running count after each element arrives, for example `Current counts: {'A': 1, 'B': 1}`
- A final frequency summary listing each element with its total count

## Files Included

| File | Description |
|------|-------------|
| `Experiment_05.ipynb` | Jupyter Notebook containing the experiment |
| `Experiment_05_Report.pdf` | Detailed experiment report |
| `README.md` | Project documentation |

## Author

Gurrala Rohith Kumar
