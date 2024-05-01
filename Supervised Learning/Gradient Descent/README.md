# Gradient Descent Algorithm

Gradient Descent is a fundamental optimization algorithm used to minimize a loss function by iteratively moving in the direction of the steepest descent. It is widely employed in machine learning for training various models, including linear regression, logistic regression, and neural networks.

![image](https://github.com/kjarjoura/INDE577/blob/main/Images/gd.png)

## Theory and Mathematics Behind Gradient Descent

Gradient Descent operates by updating the parameters (weights and bias) of a model iteratively to minimize a given loss function. The update rule for the parameters $\theta$ is given by:

$$ \theta = \theta - \alpha \nabla J(\theta) $$

where $\alpha$ is the learning rate and $\nabla J(\theta)$ is the gradient of the loss function $J(\theta)$. The gradient points in the direction of the steepest ascent, so subtracting it from the current parameter values moves the parameters in the direction of the steepest descent, towards the minimum of the loss function.

### Basic Gradient Descent

In basic Gradient Descent, the gradient is computed using the entire training dataset. The algorithm updates the parameters by taking steps proportional to the negative of the gradient of the loss function with respect to the parameters.

**Pseudocode for Gradient Descent:**

Initialize $\theta$ randomly or to zeros
  - while not converged:
    - Compute the gradient $\nabla J(\theta)$
    - Update parameters: $\theta = \theta - \alpha \nabla J(\theta)$

### Stochastic Gradient Descent (SGD)

Stochastic Gradient Descent is a variant of Gradient Descent that updates the parameters using the gradient of the loss function computed on small random subsets of the training data, known as mini-batches. This approach is computationally efficient and often converges faster than standard Gradient Descent.

![image](https://github.com/kjarjoura/INDE577/blob/main/Images/sgd.png)

**Pseudocode for Stochastic Gradient Descent (SGD):**

Initialize $\theta$ randomly or to zeros
  - while not converged:
      - Shuffle training data
      - for each mini-batch:
        - Compute the gradient $\nabla J(\theta; x^{(i)}, y^{(i)})$
     - Update parameters: $\theta = \theta - \alpha \nabla J(\theta; x^{(i)}, y^{(i)})$
   
## Applications

- **Model Training in Machine Learning**: Gradient Descent is widely used for training various machine learning models, including linear regression, logistic regression, support vector machines (SVMs), and neural networks. It enables the optimization of model parameters by minimizing a specified loss function, such as mean squared error (MSE) for regression tasks or cross-entropy loss for classification tasks.
- **Optimization in Deep Learning**: Stochastic Gradient Descent (SGD) and its variants are the optimization algorithms of choice in training deep neural networks (DNNs). These algorithms can handle large-scale datasets and high-dimensional parameter spaces typical of deep learning models. SGD variants, such as mini-batch SGD, momentum SGD, and Adam, are used to accelerate convergence, improve generalization performance, and prevent overfitting in deep learning.
- **Online Learning and Real-Time Systems**: Stochastic Gradient Descent is suitable for online learning scenarios where the data arrives sequentially or in mini-batches. It allows models to adapt continuously to changing data distributions and perform real-time updates without retraining on the entire dataset. Online learning using SGD is commonly employed in recommender systems, natural language processing (NLP), and personalized advertising.
- **Non-convex Optimization Problems**: Gradient Descent can be applied to non-convex optimization problems, where the objective function may have multiple local minima. Although Gradient Descent does not guarantee convergence to the global minimum, it can find satisfactory solutions for many practical problems. Techniques such as random restarts and simulated annealing can enhance Gradient Descent's effectiveness in exploring the solution space and escaping local minima.

## Implementation

### Linear Regression using Gradient Descent

The `LinearRegressionGD` class implements linear regression using regular Gradient Descent. It initializes the weights and bias to zeros and iteratively updates them using the gradients of the mean squared error loss function.

### Linear Regression using Stochastic Gradient Descent (SGD)

The `LinearRegressionSGD` class implements linear regression using Stochastic Gradient Descent. It shuffles the training data and iterates over mini-batches to update the weights and bias. This approach allows for faster convergence and is suitable for large datasets.

**Specific Implementation:**

The implementation in this repository uses both regular Gradient Descent and Stochastic Gradient Descent to train linear regression models. The training process is encapsulated within the `fit` method of each class, allowing for easy training and prediction using the `predict` method. Additionally, the Mean Squared Error (MSE) for each epoch is stored, enabling visualization of the training progress and convergence monitoring.
