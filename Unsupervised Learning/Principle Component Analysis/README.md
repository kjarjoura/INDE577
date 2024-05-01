## Principal Component Analysis (PCA)

Principal Component Analysis (PCA) is a powerful dimensionality reduction technique widely used in data preprocessing and exploratory data analysis. It aims to simplify the complexity of high-dimensional data while retaining its essential structure and patterns. By transforming the original features into a new set of orthogonal variables called principal components, PCA facilitates visualization, interpretation, and subsequent analysis of data.

![image](https://github.com/kjarjoura/INDE577/blob/main/Images/pca.png)

### Theory and Mathematics Behind PCA

#### Basic Idea

PCA operates by finding the directions (principal components) along which the data exhibits the most variation. It projects the data onto these directions, ranked in order of importance (by variance), thereby reducing the dimensionality while preserving most of the information. Mathematically, PCA seeks to maximize the variance of the projected data points in the transformed space.

#### Algorithm

1. **Standardization**: Standardize the dataset by subtracting the mean and dividing by the standard deviation of each feature.
2. **Covariance Matrix**: Compute the covariance matrix $C$ of the standardized data.
3. **Eigen Decomposition**: Perform eigen decomposition on the covariance matrix $C$ to obtain eigenvalues $\lambda_i$ and eigenvectors $v_i$.
4. **Selection of Principal Components**: Select the top-$k$ eigenvectors corresponding to the largest eigenvalues to form the new feature space.
5. **Projection**: Project the original data onto the new feature space defined by the selected principal components.

#### Mathematical Formulation

Given a dataset matrix $X$ with $n$ observations and $d$ features, PCA computes the eigenvectors $v_i$ and eigenvalues $\lambda_i$ of the covariance matrix $C$ as follows:

$$C = \frac{1}{n} X^T X$$

The eigen decomposition of $C$ yields:

$$C = V \Lambda V^T$$

where $V$ is the matrix containing the eigenvectors $v_i$ as columns, and $\Lambda$ is the diagonal matrix containing the eigenvalues $\lambda_i$. The principal components are given by:

$$PC_i = X \cdot v_i$$

### Parameters

- **Retained Variance**: Specifies the percentage of variance to retain in the transformed data. Higher retained variance preserves more information but may result in higher-dimensional output.

### Advantages and Limitations

#### Advantages:
- **Dimensionality Reduction**: PCA reduces the number of features while preserving most of the variance in the data.
- **Data Compression**: It compresses the data by representing it in a lower-dimensional space.
- **Noise Reduction**: PCA can filter out noise and irrelevant features, leading to improved model performance.
- **Visualization**: PCA facilitates visualization of high-dimensional data in two or three dimensions, aiding in data exploration and understanding.

#### Limitations:
- **Linear Assumption**: PCA assumes that the data lies on a linear subspace, which may not hold true for all datasets.
- **Loss of Interpretability**: The transformed features (principal components) may lack interpretability, making it challenging to explain the underlying data patterns.
- **Optimal Number of Components**: Determining the optimal number of principal components to retain can be subjective and requires careful consideration.
- **Non-Robust to Outliers**: PCA is sensitive to outliers, which can significantly influence the principal components and the resulting data transformation.

## Applications

- **Feature Extraction**: PCA is employed for feature extraction, where it identifies a set of orthogonal (uncorrelated) linear combinations of the original features, known as principal components. These principal components capture the maximum variance in the data and can be used as new features for subsequent analysis or modeling tasks.
- **Data Visualization**: PCA is a powerful tool for visualizing high-dimensional datasets in a lower-dimensional space, typically two or three dimensions. It enables the visualization of complex relationships and structures in the data, making it easier to interpret and analyze.
- **Noise Reduction**: PCA can help in reducing the effects of noise or irrelevant features in the data by focusing on the principal components that capture the most significant variations. It helps in improving the signal-to-noise ratio and enhancing the performance of downstream machine learning algorithms.
- **Clustering and Classification**: PCA is often used as a preprocessing step before clustering or classification tasks to reduce the computational complexity and improve the performance of the algorithms. By reducing the dimensionality of the feature space, PCA can lead to faster convergence and better separation of clusters or classes.
- **Anomaly Detection**: PCA can be applied in anomaly detection tasks to identify unusual patterns or outliers in high-dimensional datasets. By transforming the data into a lower-dimensional space, PCA makes it easier to detect anomalies that deviate significantly from the normal behavior of the dataset.
- **Model Interpretation**: PCA can aid in model interpretation by identifying the most important features or variables that contribute to the variance in the data. It helps in understanding the underlying structure of the dataset and identifying the key factors driving the observed patterns.

### Implementation

This repository implements a `retain_variance` function that performs PCA to retain a specified percentage of variance in the data. It utilizes the scikit-learn library's `PCA` module for computing principal components and transforming the data. The function returns the number of principal components needed to retain the specified variance.
