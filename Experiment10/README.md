# Experiment 10: Data Synopsis Generation using Bloom Filter and Count-Min Sketch

## Overview

This experiment implements two popular data synopsis techniques, the Bloom filter and the Count-Min Sketch, for efficiently representing and querying a data stream while using very small memory. The Bloom filter answers membership questions and the Count-Min Sketch estimates element frequencies, which are then compared against the exact counts.

## Project Structure

```text
Experiment_10/
│── Experiment_10.ipynb
│── Experiment_10_Report.pdf
└── README.md
```

## Technologies Used

- Python 3.x
- Hashlib module
- Jupyter Notebook

## Objectives

- Implement a Bloom filter.
- Implement a Count-Min Sketch.
- Compare the exact and approximate counts.

## Dataset

No external dataset is required. The stream is defined inside the program.

```python
stream = ["A", "B", "A", "C", "A", "B", "D", "A", "E", "A",
          "C", "B", "F", "A", "B", "A", "G", "A", "H", "A"]
```

| Element | Exact count |
|---------|------------:|
| A | 9 |
| B | 4 |
| C | 2 |
| D | 1 |
| E | 1 |
| F | 1 |
| G | 1 |
| H | 1 |

## Structure Parameters

| Structure | Parameters |
|-----------|------------|
| Bloom filter | size = 50, hash_count = 3 |
| Count-Min Sketch | width = 20, depth = 3 |

## Features

- Builds a Bloom filter from a bit array and MD5 based hash functions
- Inserts every stream element and answers membership queries
- Reports "definitely not present" when any bit is zero, otherwise "probably present"
- Builds a Count-Min Sketch as a fixed size table of counters
- Estimates the frequency of each element as the minimum of its counters
- Compares the exact count, the approximate count and the error for every element

## How to Run

1. Install Python 3.x.
2. Open `Experiment_10.ipynb` in Jupyter Notebook.
3. Run all cells in order.

No external libraries are required, as hashlib is part of the Python standard library.

## Expected Output

**Bloom filter queries**

| Element | Output |
|---------|--------|
| A | Probably present |
| B | Probably present |
| Z | Definitely not present |
| H | Probably present |

**Count-Min Sketch comparison**

A table of element, exact count, approximate count and error. With this stream and table size there are no collisions, so the error is 0 for every element.

## Files Included

| File | Description |
|------|-------------|
| `Experiment_10.ipynb` | Jupyter Notebook containing the experiment |
| `Experiment_10_Report.pdf` | Detailed experiment report |
| `README.md` | Project documentation |

## Author

Gurrala Rohith Kumar
