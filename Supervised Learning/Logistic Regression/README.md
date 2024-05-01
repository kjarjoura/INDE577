# Logistic Regression

Logistic regression is a popular statistical method used for binary classification tasks. It models the probability that a given input belongs to a particular class, making it suitable for scenarios where the dependent variable is categorical and has two outcomes.

![image](https://github.com/kjarjoura/INDE577/blob/main/Images/logr.png)

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

$$\text{log odds} = \beta_0 + \beta_1 x_1 + \beta_2 x_2 + \ldots + \beta_n x_n$$

where $\beta_0, \beta_1, \ldots, \beta_n$ are the coefficients of the logistic regression model and $x_1, x_2, \ldots, x_n$ are the input features.

3. **Apply Logistic Function**: Apply the logistic function to the log odds to obtain the predicted probabilities:

$$P(y = 1 | \mathbf{x}) = \frac{1}{1 + e^{-\text{log odds}}}$$

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

## Applications

- **Credit Scoring in Banking**: Logistic regression is widely used in banking and finance for credit scoring and risk assessment. By analyzing applicant demographics, financial history, and creditworthiness indicators, logistic regression models can predict the likelihood of default or delinquency, classify applicants into risk categories, and inform lending decisions.
- **Churn Prediction in Telecommunications**: Logistic regression is employed in the telecommunications industry for churn prediction and customer retention. By analyzing customer usage patterns, satisfaction surveys, and service quality metrics, logistic regression models can identify customers at risk of churn, personalize retention offers, and improve customer loyalty.
- **Healthcare Fraud Detection**: Logistic regression is utilized in healthcare analytics for fraud detection and claims analysis. By analyzing billing data, provider behavior, and patient medical records, logistic regression models can flag suspicious activities, detect fraudulent claims, and mitigate financial losses for insurance companies and healthcare providers.
- **Marketing Response Modeling**: Logistic regression is applied in marketing analytics for response modeling and campaign targeting. By analyzing customer demographics, purchasing history, and response to marketing campaigns, logistic regression models can predict the likelihood of customer response to promotional offers, segment customers based on their responsiveness, and optimize marketing strategies for improved ROI.

## Implementation with Scikit-Learn
In this repository, we leverage the `LogisticRegression` class from the scikit-learn library, which offers a robust implementation of logistic regression for classification tasks. This class provides a convenient interface to build, train, and evaluate logistic regression models efficiently.
