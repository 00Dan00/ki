# Use cases
- SSE: Primarily used in statistical analysis
- MAE: robust to outliers, used when avoiding penalizing large errors more
- MSE: Penalizes larger errors more
- RMSE: Provides an interpretable measure of average error in the same units as the data

# Sum of Squared Errors (SSE)
- calculates the sum of the squared differences between each predicted value and its actual value
- often used as the loss function
$$SSE = \sum_{i=1}^{n} (y_i - \hat{y}_i)^2$$
## Advantages
- penalizes large errors more heavily than small errors
- differentiable and convex (suitable for algorithms like gradiant descent)
## Disadvantages
- sensitive to outliers because of the harsher punishment

# Mean Absolute Error (MAE) L1-Loss
- calculates the average absolute difference between the predicted and actual values

$$MAE = \frac{1}{n} \sum_{i=1}^{n} |y_i - \hat{y}_i|$$

## Advantages
- less sensitive to outliers compared to SSE and RMSE
## Disadvantages
- not differentiable at zero, which can make optimization more challenging

# Mean Squared Error (MSE) L2-Loss
- the average of the SSE across all data points.
- average squared difference between the estimated values and the actual value

$$\text{MSE} = \frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2$$

# Root Mean Squared Error (RMSE)
- similar to SSE 
- measure of the average magnitude of the errors between the predicted and actual values
- square root of the average of the squared differences between the predicted and actual values
$$RMSE = \sqrt{\frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2}$$
## Advantages
- uses the same units as the original which makes it easier to understand
- also penalizes bigger errors more
## Disadvantages
- also sensitive to outlier

# Regularization Techniques
- used to prevent overfitting in regression models
- improves generalization by penalizing overly complex models
- So the Model trys to fit the algorithm + the penalty term. The weight of the penalty is defined by the regularization parameter λ

## Ridge Regression
$$\text{Objective Function} = \text{SSE} + \lambda \sum_{j=1}^{p} \beta_j^2$$

### Advantages
- shrinks the coefficients towards zero, reducing model complexity and mitigating multicollinearity
- improves generalization, particularly when the number of features is large relative to the number of observations

### Disadvantages
- Ridge regression does not perform feature selection, as it shrinks all coefficients towards zero by the same proportion.
## Lasso Regression
$$\text{Objective Function} = \text{SSE} + \lambda \sum_{j=1}^{p} |\beta_j|$$
### Advantages
- Lasso regression performs feature selection by setting some coefficients exactly to zero, effectively removing irrelevant features from the model.
- It can lead to a more interpretable model by identifying the most important features.

### Disadvantages
- Lasso tends to perform less well than Ridge when there are highly correlated features because it arbitrarily selects one feature over another.
- 