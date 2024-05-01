# K Nearest Neighbors (k-NN) Algorithm

K Nearest Neighbors (k-NN) is a simple yet powerful classification algorithm used for both regression and classification tasks. It classifies a new data point based on the majority class of its k nearest neighbors in the feature space.

![image](https://github.com/kjarjoura/INDE577/blob/main/Images/knn-1.png)

## Theory and Mathematics Behind k-NN

### Basic Idea

The k-Nearest Neighbors (k-NN) algorithm is a non-parametric, instance-based learning method used for classification and regression tasks. At its core, k-NN relies on the assumption that data points in close proximity to each other in the feature space share similar characteristics and are likely to belong to the same class.

#### Distance Metric

One of the fundamental aspects of the k-NN algorithm is the choice of distance metric to quantify the similarity or dissimilarity between data points. The most commonly used distance metric is the Euclidean distance, which measures the straight-line distance between two points in the feature space. Other distance metrics such as Manhattan distance, Minkowski distance, or cosine similarity can also be employed depending on the nature of the data and the problem domain.

### Algorithm

The k-NN algorithm can be summarized in the following steps:

1. **Choose the Number of Neighbors, k**: The value of k determines the number of nearest neighbors to consider when making predictions. A smaller value of k tends to capture local patterns in the data, while a larger value of k captures more global patterns.

2. **For each New Data Point**:
   - **Compute the Distance**: Calculate the distance between the new data point and all training examples in the feature space using the chosen distance metric.
   - **Select the k Nearest Neighbors**: Identify the k training examples with the smallest distances to the new data point.
   - **Assign Class Label**: Determine the class label of the new data point by taking a majority vote among the class labels of its k nearest neighbors. In the case of regression tasks, the predicted value can be computed as the average of the target values of the k nearest neighbors.

### Mathematical Formulation

Let $X = \{x_1, x_2, ..., x_n\}$ denote the training dataset, where each $x_i$ represents a feature vector in the feature space, and $Y = \{y_1, y_2, ..., y_n\}$ denote the corresponding class labels or target values.

For a new data point $x'$, the k-NN algorithm computes its predicted class label $\hat{y}$ or predicted target value $\hat{y}$ as follows:

- **Classification**:
  $$\hat{y} = \text{mode}(y_{i_1}, y_{i_2}, ..., y_{i_k})$$
  where $y_{i_1}, y_{i_2}, ..., y_{i_k}$ are the class labels of the k nearest neighbors of $x'$, and $\text{mode}$ represents the most frequent class label.

- **Regression**:
  $$\hat{y} = \frac{1}{k} \sum_{j=1}^{k} y_{i_j}$$
  where $y_{i_1}, y_{i_2}, ..., y_{i_k}$ are the target values of the k nearest neighbors of $x'$, and $\sum$ represents the sum of the target values.

### Considerations and Hyperparameters

#### Choice of k:
The choice of the number of neighbors, $k$, is a critical hyperparameter in k-NN. A small value of $k$ may lead to high model variance and overfitting, while a large value of $k$ may result in high model bias and underfitting. It is essential to select an appropriate value of $k$ through cross-validation or other validation techniques to achieve the best balance between bias and variance.

#### Distance Metric:
The selection of an appropriate distance metric depends on the nature of the data and the problem domain. Euclidean distance is the most commonly used metric, but other metrics such as Manhattan distance, Minkowski distance, or cosine similarity may be more suitable for certain types of data.

#### Scaling of Features:
Since k-NN relies on the computation of distances between data points, it is crucial to scale the features to ensure that no single feature dominates the distance calculations. Standardization or normalization of features can help achieve a more balanced contribution from each feature to the distance metric.

### Advantages and Limitations

#### Advantages:
- Simple and easy to understand.
- No assumptions about the underlying data distribution.
- Suitable for both classification and regression tasks.
- Can capture complex decision boundaries.

#### Limitations:
- Computationally expensive, especially for large datasets.
- Sensitivity to the choice of hyperparameters, especially $k$.
- Performance may degrade in high-dimensional feature spaces.
- Not suitable for imbalanced datasets or noisy data.

## Implementation with Sci-Kit Learn
The implementation in this repository uses the `KNeighborsClassifier` class from scikit-learn to classify data points based on their nearest neighbors. It visualizes the decision boundaries and provides insights into the performance of the classifier for different values of $k$.
