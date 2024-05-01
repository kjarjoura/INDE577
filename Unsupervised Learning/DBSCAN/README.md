# DBSCAN (Density-Based Spatial Clustering of Applications with Noise)

DBSCAN is a density-based clustering algorithm that groups together closely packed points based on density. It is particularly effective in identifying clusters of arbitrary shapes and handling noise in the data.

![image](https://github.com/kjarjoura/INDE577/blob/main/Images/bdscan.png)

## Theory and Mathematics Behind DBSCAN

### Basic Idea

DBSCAN (Density-Based Spatial Clustering of Applications with Noise) is a clustering algorithm that groups together closely packed points based on density. Unlike K-means, which requires the number of clusters to be specified in advance, DBSCAN is capable of discovering clusters of arbitrary shapes and sizes.

### Density Reachability and Core Points

DBSCAN identifies core points, which are data points surrounded by at least a specified number of neighboring data points within a given distance (eps). These core points are at the heart of dense regions in the dataset and form the basis of cluster formation.

### Neighbor and Border Points

Points that are not core points but fall within the neighborhood distance of a core point are considered neighbor points. These points may belong to the same cluster as the core point but are not dense enough to be classified as core points themselves. Border points lie on the periphery of clusters and are reachable from core points but do not have enough neighbors to be classified as core points themselves.

### Algorithm

1. **Initialization**: Specify the neighborhood radius (eps) and the minimum number of points required to form a dense region ($min_{samples}$).
2. **Core Point Identification**: Identify core points, which have at least $min_{samples}$ within distance eps.
3. **Cluster Formation**: Form clusters by assigning core points and their neighbors to the same cluster.
4. **Noise Detection**: Mark points that do not belong to any cluster as noise or outliers.

### Mathematical Formulation

#### Density Reachability

A point $p$ is said to be density-reachable from another point $q$ if there exists a chain of points $p_1, p_2, \ldots, p_n$ such that $p_1 = q$, $p_n = p$, and each $p_i$ is a core point with $p_{i+1}$ as its neighbor.

#### Density Connectivity

Two points $p$ and $q$ are density-connected if there exists a core point $o$ such that both $p$ and $q$ are density-reachable from $o$.

![image](https://github.com/kjarjoura/INDE577/blob/main/Images/dbscanalg.png)

### Model Parameters

- **eps**: The maximum distance between two samples for one to be considered as in the neighborhood of the other.
- **min_samples**: The number of samples in a neighborhood for a point to be considered as a core point.

## Advantages and Limitations
**Advantages**:
  - Capable of identifying clusters of arbitrary shapes and sizes.
  - Robust to noise and outliers.
  - Does not require the number of clusters to be specified in advance.
  
**Limitations**:
  - Sensitivity to parameters: Performance may be sensitive to the choice of eps and min_samples.
  - Memory and computational complexity: The algorithm's complexity grows with the size of the dataset, impacting scalability.
  - Difficulty in identifying global clusters: DBSCAN may struggle to identify clusters with varying densities.

## Implementation with Scikit-Learn

In this implementation, we use the `DBSCAN` class from scikit-learn, a popular machine learning library in Python. The code fits the DBSCAN model to the data, assigns cluster labels, and estimates the number of clusters and noise points in the dataset.
