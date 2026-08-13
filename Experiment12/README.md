# Experiment 12: Cluster Streaming Data Using Single-Pass K-Means Algorithm

## Overview

This experiment performs real time clustering of streaming data using the incremental single-pass K-Means algorithm. Each observation is read exactly once, assigned to the nearest centroid, used to update that centroid immediately with a running mean, and then discarded. The cluster quality is measured with the silhouette score and compared against conventional K-Means.

## Project Structure

```text
Experiment_12/
│── Experiment_12.ipynb
│── Experiment_12_Report.pdf
└── README.md
```

## Technologies Used

- Python 3.x
- NumPy
- Pandas
- Matplotlib
- Scikit-learn
- Jupyter Notebook

## Data Pipeline

```text
Streaming data input -> Complete dataset -> Choose k centroids -> Assign all data points
-> Recalculate the centroid -> Find the accuracy -> Reconstruct the cluster as new data points arrive
```

## Update Rule

```text
learning_rate = 1 / count[cluster]

centroid = centroid + learning_rate * (x - centroid)
```

## Dataset

No external dataset is required. The stream is generated at runtime.

| Group | Observations | Centre | Scale |
|-------|-------------:|--------|------:|
| clusters_1 | 300 | (2, 2) | 0.6 |
| clusters_2 | 300 | (8, 8) | 0.7 |
| clusters_3 | 300 | (5, 2) | 0.5 |

| Parameter | Value |
|-----------|------:|
| Total observations | 900 |
| Number of clusters (k) | 3 |
| Random seed | 42 |

The three groups are stacked with `np.vstack()` and shuffled so that the observations arrive in random order, exactly like a real stream.

## Procedural Steps

1. Generate or acquire streaming data.
2. Process one observation at a time.
3. Maintain k cluster centroids.
4. Assign every incoming data point.
5. Update the selected centroid immediately.
6. Avoid storing the complete stream.
7. Visualize cluster formation.
8. Measure the cluster quality.
9. Compare the streaming result with conventional K-Means.
10. Result analysis.

## Features

- Uses the first k observations as the initial centroids
- Processes each observation exactly once
- Finds the nearest centroid using the Euclidean distance
- Updates the selected centroid immediately with the learning rate 1 / count
- Stores only k centroids and k counts, never the stream itself
- Records the centroid history so the cluster formation can be traced
- Measures the silhouette score
- Compares the result against conventional K-Means

## How to Run

1. Install Python 3.x.
2. Install the required libraries.

```bash
pip install numpy pandas matplotlib scikit-learn
```

3. Open `Experiment_12.ipynb` in Jupyter Notebook.
4. Run all cells in order.

## Expected Output

```text
Final Centroids:
Cluster 0: Feature_1=8.529, Feature_2=8.482
Cluster 1: Feature_1=3.503, Feature_2=2.022
Cluster 2: Feature_1=7.760, Feature_2=7.752

Cluster counts:
Cluster 0: 123 observations
Cluster 1: 600 observations
Cluster 2: 177 observations

Silhouette_score: 0.5661
```

A scatter plot of the three clusters with the final centroids marked by crosses is also displayed.

## Comparison with Conventional K-Means

| Method | Silhouette | WCSS | Passes |
|--------|-----------:|-----:|-------:|
| Single-Pass K-Means | 0.5661 | 1931.72 | 1 |
| Conventional K-Means | 0.7275 | 643.23 | 2 iterations |

With the seed 42, two of the first three observations fall in the region around (8, 8), so two centroids start in the same group and the groups near (2, 2) and (5, 2) merge into one cluster of 600 observations. This is the main limitation of the single-pass method: there is no second pass to correct a poor initialization.

## Files Included

| File | Description |
|------|-------------|
| `Experiment_12.ipynb` | Jupyter Notebook containing the experiment |
| `Experiment_12_Report.pdf` | Detailed experiment report |
| `README.md` | Project documentation |

## Author

Gurrala Rohith Kumar
