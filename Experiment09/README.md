# Experiment 9: Real-Time Bitcoin Price Analysis using a Sliding Window

## Overview

This experiment fetches live Bitcoin prices from the CoinGecko API at regular intervals and stores the most recent values in a fixed size sliding window built with a `deque`. Once the window is full, statistical analysis is performed after every new price so that short-time market fluctuations can be monitored continuously.

## Project Structure

```text
Experiment_09/
│── Experiment_09.ipynb
│── Experiment_09_Report.pdf
└── README.md
```

## Technologies Used

- Python 3.x
- Requests
- Collections module (`deque`)
- Statistics module
- Time module
- Jupyter Notebook

## Data Source

Live market data is fetched from the CoinGecko public API.

```text
Endpoint : https://api.coingecko.com/api/v3/simple/price
Params   : ids=bitcoin, vs_currencies=usd
```

| Parameter | Value |
|-----------|------:|
| Number of readings | 10 |
| Interval between readings | 10 seconds |
| Window size | 5 |
| Request timeout | 10 seconds |

## Features

- Fetches the live Bitcoin price in USD from the CoinGecko API
- Handles network and API errors using a try-except block
- Validates the API response before reading the price
- Maintains a sliding window of the five most recent prices using `deque(maxlen=5)`
- Automatically drops the oldest price when a new one arrives
- Calculates mean, median, minimum, maximum and standard deviation for each full window

## How to Run

1. Install Python 3.x.
2. Install the required library.

```bash
pip install requests
```

3. Open `Experiment_09.ipynb` in Jupyter Notebook.
4. Run all cells in order.

An active internet connection is required. The program takes about 100 seconds to complete, since it waits 10 seconds between readings.

## Expected Output

The notebook displays:

- The reading number and the current Bitcoin price in USD for each of the 10 readings
- Once five prices are collected, the sliding window contents followed by the mean, median, minimum, maximum and standard deviation
- An error message instead of a price if the API call fails, without stopping the program

The actual prices depend on the live market at the time the program is run.

## Files Included

| File | Description |
|------|-------------|
| `Experiment_09.ipynb` | Jupyter Notebook containing the experiment |
| `Experiment_09_Report.pdf` | Detailed experiment report |
| `README.md` | Project documentation |

## Author

Gurrala Rohith Kumar
