# Experiment 4: Packet Arrival Stream Processing

## Overview

This experiment simulates a network packet arrival stream using Python. Packets of random sizes are generated one after another, each arrival is printed as it happens, and the complete stream is visualized using a line plot to show how packet size varies over time.

## Project Structure

```text
Experiment_04/
│── Experiment_04.ipynb
│── Experiment_04_Report.pdf
└── README.md
```

## Technologies Used

- Python 3.x
- Random module
- Time module
- Matplotlib
- Jupyter Notebook

## Dataset

No external dataset is required. The packet stream is generated at runtime.

| Parameter | Value |
|-----------|------:|
| Number of packets | 20 |
| Minimum packet size | 64 bytes |
| Maximum packet size | 1500 bytes |
| Delay between arrivals | 0.2 seconds |

## Features

- Generates a stream of 20 network packets
- Assigns each packet a random size between 64 and 1500 bytes
- Prints each packet as it arrives
- Simulates arrival delay using the time module
- Plots packet size against packet number
- Helps identify traffic patterns and bursts

## How to Run

1. Install Python 3.x.
2. Install the required library.

```bash
pip install matplotlib
```

3. Open `Experiment_04.ipynb` in Jupyter Notebook.
4. Run all cells in order.

## Expected Output

The notebook displays:

- A line for each packet, for example `Packet 1 arrived: 842 bytes`
- A line plot of packet size versus packet number with circular markers

## Files Included

| File | Description |
|------|-------------|
| `Experiment_04.ipynb` | Jupyter Notebook containing the experiment |
| `Experiment_04_Report.pdf` | Detailed experiment report |
| `README.md` | Project documentation |

## Author

Gurrala Rohith Kumar
