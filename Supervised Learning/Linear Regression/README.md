# Linear Regression

Linear regression is one of the simplest and most commonly used statistical techniques for modeling the relationship between a dependent variable (target) and one or more independent variables (predictors). It assumes a linear relationship between the independent variables and the dependent variable, which can be represented by a straight line.

![image](https://github.com/kjarjoura/INDE577/blob/main/Images/lr.png)

## Theory and Mathematics Behind Linear Regression

### Basic Idea

Linear regression is a statistical method used to model the relationship between a dependent variable and one or more independent variables by fitting a linear equation to the observed data. It assumes a linear relationship between the independent and dependent variables, where the dependent variable can be predicted as a linear combination of the independent variables.

### Algorithm

Linear regression aims to find the "best-fitting" line through the data points, which minimizes the sum of squared differences between the observed and predicted values. The linear regression algorithm typically involves the following steps:

1. **Calculate Slope and Intercept**: The slope and intercept of the regression line are calculated using the least squares method, minimizing the sum of squared residuals between the observed and predicted values.

2. **Make Predictions**: Once the slope and intercept are determined, predictions can be made for new input data points using the linear regression equation.

3. **Evaluate Model Performance**: Various metrics such as R-squared, correlation coefficient, and covariance can be calculated to assess the goodness of fit of the linear regression model and its predictive power.

### Mathematical Formulation

#### Slope Calculation:
The slope of the regression line ($\beta_1$) is calculated using the formula:

$$\beta_1 = \frac{n \sum(x_iy_i) - \sum(x_i) \sum(y_i)}{n \sum(x_i^2) - (\sum(x_i))^2}$$

where $n$ is the number of data points, $x_i$ and $y_i$ are the independent and dependent variables, respectively.

#### Intercept Calculation:
The intercept of the regression line ($\beta_0$) is calculated using the formula:

$$\beta_0 = \bar{y} - \beta_1 \bar{x}$$

where $\bar{x}$ and $\bar{y}$ are the means of the independent and dependent variables, respectively.

#### Making Predictions:
Predictions ($\hat{y}$) for new input data points can be made using the linear regression equation:

$$\hat{y} = \beta_1 x + \beta_0$$

where $x$ represents the input variable.

#### Evaluation Metrics:
- **R-squared**: Indicates the proportion of the variance in the dependent variable that is predictable from the independent variable(s).
- **Correlation Coefficient**: Measures the strength and direction of the linear relationship between two variables.
- **Covariance**: Measures the degree to which two variables change together.

### Advantages and Limitations

#### Advantages
- Simple and easy to understand.
- Provides interpretable coefficients to explain the relationship between variables.
- Can handle both continuous and categorical independent variables.

#### Limitations
- Assumes a linear relationship, which may not always be appropriate.
- Sensitive to outliers and multicollinearity.
- Requires the independence and normality of residuals assumptions to be met for accurate inference.

### Implementation

This repository demonstrates the implementation of linear regression using Python. It includes functions to calculate the slope, intercept, make predictions, and evaluate model performance using metrics such as R-squared and correlation coefficient. The linear regression line is then plotted to visualize the relationship between the independent and dependent variables.

