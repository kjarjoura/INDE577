# Decision Trees

Decision Trees are a popular class of supervised learning algorithms used for both classification and regression tasks. They are particularly attractive due to their simplicity, interpretability, and ability to handle both numerical and categorical data.

![image](https://github.com/kjarjoura/INDE577/blob/main/Images/dt.png)

## Theory and Mathematics Behind Decision Trees

### Decision Tree Structure
A Decision Tree consists of nodes and directed edges. Each internal node represents a decision based on a feature, and each leaf node represents a class label or regression value. The tree is constructed recursively by partitioning the feature space into smaller regions until certain stopping criteria are met, such as maximum depth or minimum samples per leaf.

### Splitting Criteria
Decision Trees make splits based on a splitting criterion, such as Gini impurity or entropy. These criteria measure the homogeneity of a set of samples. Gini impurity measures the probability of misclassifying a randomly chosen sample if it were labeled according to the distribution of classes in the node. Entropy, on the other hand, measures the average information content of a set of samples.

### Gini Impurity
The Gini impurity for a node $t$ with $K$ classes is defined as:
$$G(t) = 1 - \sum_{i=1}^{K} p(i|t)^2$$
where $p(i|t)$ is the proportion of samples of class $i$ in node $t$.

### Entropy
The entropy for a node $t$ with $K$ classes is defined as:
$$H(t) = - \sum_{i=1}^{K} p(i|t) \log_2 p(i|t)$$

### Information Gain
The goal of splitting is to maximize the information gain, which is the difference between the impurity of the parent node and the weighted sum of impurities of the child nodes. It is defined as:
$$\text{Information Gain} = I(\text{parent}) - \sum_{\text{children}} \frac{N_j}{N} I(\text{child}_j)$$
where $N$ is the total number of samples, $N_j$ is the number of samples in the $j^{th}$ child node, and $I$ represents the impurity measure (Gini impurity or entropy).

### Tree Pruning
Decision Trees are prone to overfitting, especially when the tree grows deep. Pruning techniques such as cost complexity pruning (also known as weakest link pruning) can be used to prevent overfitting by removing nodes that do not contribute significantly to the overall performance of the tree.

### Decision Tree Algorithm

1. Initialize the tree by selecting the attribute that maximizes the information gain or minimizes impurity as the root node.
2. For each internal node in the tree:
   - a. Evaluate the splitting criteria to determine the optimal attribute for further partitioning.
   - b. Partition the data into subsets based on the selected attribute's values.
   - c. Recursively apply steps 2a and 2b to each subset until a stopping criterion is met, such as reaching a maximum depth or minimum number of samples.
3. Assign class labels or regression values to the leaf nodes based on the majority class or average target value within each partition.
4. For a new instance, traverse the tree from the root node to a leaf node by following the decision paths based on the attribute values.
5. Predict the class label or regression value associated with the leaf node reached during traversal.

#### Attribute Selection Measures:
- Entropy (Information Gain):
  - Evaluate the entropy of the dataset and each attribute to quantify the uncertainty or randomness in the data.
  - Select the attribute with the highest information gain, calculated as the difference between the entropy of the parent node and the weighted average entropy of the child nodes.
- Gini Impurity:
  - Assess the impurity of the dataset and each attribute to measure the probability of misclassifying a randomly chosen sample.
  - Choose the attribute that minimizes the Gini impurity, computed as the sum of squared probabilities of each class in a node.

## Implementation in scikit-learn
In this repository, we utilize the `DecisionTreeClassifier` class from the scikit-learn library, which provides an efficient implementation of Decision Trees for classification tasks. This class allows us to easily construct, train, and evaluate Decision Tree models using various splitting criteria, such as Gini impurity or entropy. Additionally, scikit-learn provides functionalities for tree pruning and fine-tuning hyperparameters to optimize model performance.
