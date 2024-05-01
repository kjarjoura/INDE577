# The Perceptron

The perceptron is a fundamental building block of neural networks, representing the simplest form of a single-layer neural network. It is used for binary classification tasks and learns a linear decision boundary to separate data points of different classes.

![image](https://github.com/kjarjoura/INDE577/blob/main/Images/per.png)


## Theory and Mathematics Behind The Perceptron

### Basic Idea

The Perceptron algorithm is based on the concept of a linear threshold unit (LTU), which takes input features, applies weights to them, sums them up, and then passes the result through an activation function to produce a binary output. The algorithm iteratively adjusts the weights to minimize classification errors until convergence.

### Algorithm

1. **Initialization**: Initialize the weights and bias (if applicable) randomly or to zero.
2. **Training**:
   - Iterate over the training dataset.
   - For each instance, compute the predicted class using the current weights.
   - Update the weights based on the prediction error and learning rate.
   - Continue until convergence or for a maximum number of iterations.
3. **Prediction**: Given a new instance, compute the weighted sum of features and apply the activation function to predict the class.

### Mathematical Formulation

#### Weight Function:
The Perceptron algorithm updates the weights ($w$) according to the formula:

$$w_{i+1} = w_i + \eta \cdot (y - \hat{y}) \cdot x$$

where:
- $w_{i+1}$ is the updated weight.
- $\eta$ is the learning rate.
- $y$ is the true label.
- $\hat{y}$ is the predicted label.
- $x$ is the feature vector.

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
  
#### Parameter Tuning:
Parameter tuning involves selecting optimal values for the learning rate, maximum iterations, and other hyperparameters to improve model performance and convergence speed. Techniques such as grid search or random search can be used to search the hyperparameter space and identify the best combination of parameters.

## Advantages and Limitations

### Advantages:
- Simplicity: The Perceptron algorithm is straightforward to implement and understand.
- Speed: It can converge quickly, especially for linearly separable data.
- Memory Efficiency: Requires minimal memory as it processes data instances sequentially.

### Limitations:
- Linearity Assumption: The model assumes linear separability, limiting its applicability to linearly separable datasets.
- Convergence: It may not converge if the data is not linearly separable, leading to infinite loops.
- Sensitivity to Scaling: Performance may be affected by feature scaling, especially when using a learning rate.

## Implementation

The implementation in this repository is a custom implementation of the perceptron algorithm in Python. The `Perceptron` class encapsulates the functionality of the perceptron model, including methods for initialization, forward propagation, weight updates, model fitting, and prediction. It allows for customization of parameters such as bias inclusion, learning rate, and maximum iterations.
