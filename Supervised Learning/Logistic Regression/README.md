# Logistic Regression

Logistic regression is a popular statistical method used for binary classification tasks. It models the probability that a given input belongs to a particular class, making it suitable for scenarios where the dependent variable is categorical and has two outcomes.

## Theory and Mathematics Behind Logistic Regression

### Basic Idea

Logistic regression models the probability that an instance belongs to a particular class using the logistic function, also known as the sigmoid function. It estimates the probability by fitting a linear equation to the input features and then applying the logistic function to the result.

### Algorithm

# Logistic Regression

Logistic regression is a popular statistical method used for binary classification tasks. It models the probability that a given input belongs to a particular class, making it suitable for scenarios where the dependent variable is categorical and has two outcomes.

## Algorithm

Logistic regression aims to find the parameters of the logistic function that best fit the data. The algorithm involves the following steps:

1. **Initialize Parameters**: Initialize the parameters of the logistic function, including the intercept and coefficients.

2. **Calculate Log Odds**: Compute the log odds of the positive class for each instance using the logistic function:

$$\text{log\textsubscript{odds}} = \beta_0 + \beta_1 x_1 + \beta_2 x_2 + \ldots + \beta_n x_n$$

where $\beta_0, \beta_1, \ldots, \beta_n$ are the coefficients of the logistic regression model and $x_1, x_2, \ldots, x_n$ are the input features.

3. **Apply Logistic Function**: Apply the logistic function to the log odds to obtain the predicted probabilities:

$$P(y = 1 | \mathbf{x}) = \frac{1}{1 + e^{-\text{log\textsubscript{odds}}}}$$

4. **Thresholding**: Convert the predicted probabilities into binary class labels using a threshold (e.g., 0.5).

5. **Training**: Use optimization algorithms like gradient descent or Newton-Raphson method to maximize the log-likelihood function and estimate the model parameters $\beta_0, \beta_1, \ldots, \beta_n$.

6. **Prediction**: After training, use the learned model to predict the probability of the positive class for new data points.


### Mathematical Formulation

Logistic regression uses the logistic function to model the probability that an instance belongs to a particular class:

$$P(y = 1 | x) = \frac{1}{1 + e^{-(\beta_0 + \beta_1x_1 + \beta_2x_2 + \ldots + \beta_nx_n)}}$$

where $P(y = 1 | x)$ is the probability that the instance belongs to class 1 given the input features $x$, and $\beta_0, \beta_1, \ldots, \beta_n$ are the coefficients of the logistic regression model.

The logistic function is defined as:

$$\sigma(z) = \frac{1}{1 + e^{-z}}$$

where $z = \beta_0 + \beta_1x_1 + \beta_2x_2 + \ldots + \beta_nx_n$ is the linear combination of input features and coefficients.

### Maximum Likelihood Estimation

In logistic regression, the parameters $\beta_0, \beta_1, \ldots, \beta_n$ are estimated using maximum likelihood estimation (MLE). The goal is to maximize the likelihood function, which measures the probability of observing the given set of outcomes given the model parameters.

### Advantages and Limitations

#### Advantages
- Suitable for binary classification tasks.
- Provides probabilistic interpretations of predictions.
- Can handle both continuous and categorical independent variables.

#### Limitations
- Assumes a linear relationship between the independent variables and the log odds of the dependent variable.
- May not perform well with highly correlated features.
- Requires careful interpretation of coefficients.
