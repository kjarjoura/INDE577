# K-Means Clustering

K-Means is a partitioning clustering algorithm widely used for grouping data points into K distinct clusters. It is an iterative algorithm that aims to minimize the variance within clusters by iteratively assigning data points to the nearest cluster centroid and updating the centroids to the mean of the data points within each cluster.

![image](https://github.com/kjarjoura/INDE577/blob/main/Images/kmc.png)

## Theory and Mathematics Behind K-Means Clustering

### Basic Idea

K-Means clustering aims to minimize the within-cluster sum of squared distances between data points and their respective cluster centroids. The algorithm iteratively assigns data points to the nearest centroid and updates the centroids until convergence.

### Algorithm

1. **Initialization**: Randomly initialize $K$ cluster centroids.
2. **Assignment**: Assign each data point to the nearest centroid.
3. **Update**: Recalculate the centroids as the mean of the data points in each cluster.
4. **Convergence**: Repeat steps 2 and 3 until convergence criteria are met (e.g., no significant change in centroids or maximum iterations reached).

### Parameters
- Number of Clusters (K): Specifies the desired number of clusters to partition the dataset into. This parameter needs to be predefined based on domain knowledge or exploration of the data.

- Maximum Iterations: Determines the maximum number of iterations the algorithm will perform before considering convergence. Setting a maximum iteration limit helps prevent the algorithm from running indefinitely, especially when convergence criteria are not met.

- Convergence Threshold (Epsilon): Represents the criterion for determining when the algorithm has converged. Convergence is typically achieved when the change in centroids between consecutive iterations falls below this threshold.

### Mathematical Formulation

#### Objective Function:
The objective function of K-Means clustering is to minimize the within-cluster sum of squared distances:

$$J = \sum_{i=1}^{K} \sum_{\mathbf{x} \in C_i} \| \mathbf{x} - \mathbf{\mu}_i \|^2$$

where $C_i$ represents the $i$-th cluster, $\mathbf{\mu}_i$ is the centroid of cluster $C_i$, and $\| \cdot \|$ denotes the Euclidean distance.

#### Cluster Assignment:
Data points are assigned to the nearest cluster centroid based on the Euclidean distance:

$$\text{argmin}_{j} \| \mathbf{x} - \mathbf{\mu}_j \|$$

### Advantages and Limitations

#### Advantages:
- Simple and intuitive algorithm.
- Efficient for large datasets.
- Works well with spherical clusters.

#### Limitations:
- Requires the number of clusters to be specified in advance.
- Sensitive to the initial placement of centroids.
- Assumes clusters are isotropic and equally sized.

## Implementation
This repostiory implements a `KMeansClustering` class that offers a flexible interface for K-Means Clustering, allowing users to set parameters such as the number of clusters, maximum iterations, and convergence threshold during initialization. It provides essential methods like initialization, fitting the model to data, predicting cluster labels for new data points, and calculating the mean squared error for the final clusters.
