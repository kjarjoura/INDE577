# Ensemble Methods

Ensemble methods in machine learning combine multiple individual models to produce a stronger predictive model. These methods leverage the wisdom of the crowd by aggregating predictions from diverse models to improve overall performance. Among the most popular ensemble methods are Random Forests and Bagging. Let's explore the theory behind these methods and how they are implemented.

## Theory and Mathematics Behind Ensemble Methods

### Random Forests

Random Forests are an ensemble learning technique based on decision trees. They operate by constructing a multitude of decision trees during training and outputting the mode of the classes (classification) or mean prediction (regression) of the individual trees.

#### Decision Trees

A decision tree is a hierarchical structure composed of nodes that represent decision points and branches that represent possible outcomes. Each internal node corresponds to a feature, and each leaf node corresponds to a class label or prediction.

#### Bootstrap Aggregating (Bagging)

Random Forests use a technique called Bootstrap Aggregating (Bagging) to create multiple independent decision trees. Bagging involves randomly sampling the training dataset with replacement to generate multiple subsets. Each subset is then used to train a decision tree independently.

#### Feature Randomness

In addition to bagging, Random Forests introduce randomness at the feature level. At each node of a decision tree, only a random subset of features is considered for splitting, which helps decorrelate the individual trees and improve diversity.

#### Prediction Aggregation

During inference, predictions from all individual trees are aggregated to produce the final prediction. For classification tasks, the mode of the class predictions is taken, while for regression tasks, the mean prediction is computed.

#### Mathematical Formulation

Let $X = {x_1, x_2, ..., x_n}$ denote the training dataset, and $Y = {y_1, y_2, ..., y_n}$ denote the corresponding labels. A Random Forest consists of $T$ decision trees, denoted as ${T_1, T_2, ..., T_T}$. Each decision tree $T_i$ is trained on a bootstrap sample $X_i$ of size $n'$, where $n'$ is typically equal to $n$, and a random subset of features is considered at each node.

The prediction of the Random Forest $\hat{Y}$ for a new instance $x'$ is obtained by aggregating the predictions of all individual trees:
$$\hat{Y}(x') = \text{mode}(\{T_1(x'), T_2(x'), ..., T_T(x')\})$$

### Bagging

Bagging is a general-purpose ensemble method that can be applied to any base learning algorithm. It aims to reduce variance and prevent overfitting by training multiple models independently on different subsets of the training data and averaging their predictions.

#### Base Estimator

The base estimator refers to the underlying learning algorithm used to train each individual model within the ensemble. It can be any machine learning model, such as decision trees, SVMs, or neural networks.

#### Bootstrap Sampling

Bagging employs bootstrap sampling to create diverse training subsets. In bootstrap sampling, data points are randomly sampled with replacement from the original training dataset to form new training sets of equal size.

#### Aggregation

After training multiple base estimators on bootstrap samples, Bagging aggregates their predictions using averaging (for regression) or voting (for classification). This aggregation process helps improve generalization performance and reduce overfitting.

#### Mathematical Formulation

Let $X = \{x_1, x_2, ..., x_n\}$ denote the training dataset, and $Y = \{y_1, y_2, ..., y_n\}$ denote the corresponding labels. Bagging consists of $B$ base estimators, denoted as $\{E_1, E_2, ..., E_B\}$. Each base estimator $E_i$ is trained on a bootstrap sample $X_i$ of size $n'$, where $n'$ is typically equal to $n$.

The prediction of the Bagging ensemble $\hat{Y}$ for a new instance $x'$ is obtained by averaging the predictions of all individual base estimators:
$$\hat{Y}(x') = \frac{1}{B} \sum_{i=1}^{B} E_i(x')$$

## Implementation in scikit-learn

In this repository, we utilize the `RandomForestClassifier` and `BaggingClassifier` classes from the scikit-learn library to implement Random Forests and Bagging, respectively. These classes provide efficient implementations of ensemble methods for classification tasks. By leveraging scikit-learn's functionalities, we can easily construct, train, and evaluate ensemble models using various hyperparameters and splitting criteria, such as Gini impurity or entropy. Additionally, scikit-learn offers tools for fine-tuning hyperparameters and optimizing model performance, making it a valuable resource for ensemble learning tasks.

