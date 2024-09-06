## Stochastic Gradient Descent (SGD)
- Computes Gradients and updates the weights after every after each individual trainings example (or small batch of examples)
- Can converge faster and handle larger datasets more efficiently
- but could lead to instability due to updates after each example
$$\theta := \theta - \alpha \nabla_\theta J(\theta; x^{(i)}, y^{(i)})$$
$(x^{(i)}, y^{(i)})$: is a single training example
## Batch Gradient Descent
- Computes Gradient over the entire dataset before updating weights
- Converges smoother than SGD but can be slower due to the massive overhead of larger datasets
$$\theta := \theta - \alpha \nabla_\theta J(\theta)$$
θ: represents the model parameters (weights and biases).
α: is the learning rate
∇θ​J(θ) is the gradient of the loss function
## Mini-batch Gradient Descent
- Compromise between SGD and Batch Gradient Descent 
- Gradient computed and weights updated after processing a small batch of data (usually between 16-256)
- Faster convergence than batch GD and more stable convergence than SGD
$$\theta := \theta - \alpha \frac{1}{m} \sum_{i=1}^m \nabla_\theta J(\theta; x^{(i)}, y^{(i)})$$
