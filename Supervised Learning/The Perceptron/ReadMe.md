# The Perceptron

The perceptron is a fundamental building block of neural networks, representing the simplest form of a single-layer neural network. It is used for binary classification tasks and learns a linear decision boundary to separate data points of different classes.

## Theory and Mathematics Behind The Perceptron

### Basic Idea

The Perceptron algorithm learns a linear decision boundary to classify input data into two categories. It takes a set of input features and assigns weights to each feature, along with an additional weight for the bias term. The weighted sum of the input features is then passed through an activation function (step function), which produces the final output prediction.

### Algorithm

The perceptron algorithm involves the following steps:

1. **Initialization**: Initialize the weights and bias term randomly or to zeros.

2. **Forward Propagation**: Compute the weighted sum of the input features and apply the activation function to produce the output prediction.

3. **Update Weights**: If the prediction is incorrect, update the weights using the gradient descent update rule to minimize the loss.

4. **Repeat**: Repeat steps 2 and 3 until convergence or a maximum number of iterations is reached.

### Mathematical Formulation

#### Activation Function:
The perceptron uses a step function as its activation function, defined as:

$$f(x) = 
\begin{cases} 
1 & \text{if } x \cdot y > 0 \\
-1 & \text{otherwise}
\end{cases}$$

where $x$ is the feature vector and $y$ is the weight vector.

#### Loss Function:
The loss function for the perceptron is the squared error loss, given by:

$$L = \sum_{i=1}^{N} 0.5 \times \left( f(w, x_i) - y_i \right)^2$$

where $N$ is the number of data points, $x_i$ is the feature vector, $y_i$ is the true label, and $w$ is the weight vector.

### Model Parameters and Parameter Tuning

#### Model Parameters:
- **Bias**: Bias is a constant term added to the input of each perceptron neuron. It allows the model to fit the data better by shifting the decision boundary away from the origin. When the bias is included in the model, each perceptron has an additional weight associated with it, which represents the bias.
- **Learning Rate**: The learning rate controls the step size of weight updates during the training process. It determines how much the weights are adjusted in response to the error calculated during each iteration of training. A higher learning rate allows the model to converge faster but may lead to instability and overshooting the optimal solution. Conversely, a lower learning rate may result in slower convergence but can lead to more stable and accurate results. Tuning the learning rate is crucial for balancing training speed and model performance.
- **Maximum Iterations**: This parameter defines the maximum number of iterations (or epochs) the perceptron algorithm will perform during training. An iteration refers to one complete pass through the entire dataset. Setting a maximum number of iterations prevents the algorithm from running indefinitely and helps control the training time. If the algorithm does not converge within the specified maximum iterations, training will stop even if the model has not yet reached optimal performance.
- 
#### Parameter Tuning:
Parameter tuning involves selecting optimal values for the learning rate, maximum iterations, and other hyperparameters to improve model performance and convergence speed. Techniques such as grid search or random search can be used to search the hyperparameter space and identify the best combination of parameters.

## Implementation

The implementation in this repository is a custom implementation of the perceptron algorithm in Python. The `Perceptron` class encapsulates the functionality of the perceptron model, including methods for initialization, forward propagation, weight updates, model fitting, and prediction. It allows for customization of parameters such as bias inclusion, learning rate, and maximum iterations.
