### Hyperplane
- find the Hyperplane (n-1) that seperates the data into classes.
### Margin
- <u>Margin</u>: distance between the hyperplane and the nearest data point from either class
- SVM aims to maximize this margin => maximum margin classifier (biggest street)
### Support Vectors
- data points that are closest to the hyperplane and thus define the position and orientation of the hyperplane. They are critical for the SVM's decision boundary.

### Optimization Objective
- maximize the margin while correctly classifying the data points. 
- constrained optimization problem (solved using techniques such as quadratic programming)
$$\min_{w, b} \frac{1}{2} \|w\|^2$$
subject to:
$$y_i (w \cdot x_i + b) \geq 1 \quad \forall i$$
w : normal vector the the hyperplane
b : bias term
xi : training data points
yi : class labels


# Soft Margin
- allows some misclassification in order to get a better generalized fit for unseen data or when data is not perfectly linearly separable.
- Slack Variables $(ξi)$ are introduced to allow some data points to be within the margin or even on the wrong side of the hyperplane. These slack variables measure the degree of misclassification of each data point.
- Objective is to find a balance between maximizing the margin and minimizing the classification error. This is achieved by modifying the SVM optimization problem to include a penalty term for the slack variables.
- Regularization Parameter (C) controls the trade-off between maximizing the margin and minimizing the classification error. Small C allows more slack, bigger C allows less slack
$$\min_{w, b, \xi} \frac{1}{2} \|w\|^2 + C \sum_{i=1}^{N} \xi_i$$

subject to:
$$y_i (w \cdot x_i + b) \geq 1 - \xi_i$$
$$ξi​≥0,$$

# Kernel Trick
- so far SVM can only do linear classification. 
- The Kernel Trick enables it to also do non-linear classification.
- Involves transforming the original feature space into a higher-dimensional space using a kernel function.
- it does that without explicitly computing the coordinate in that space 

## Kernel functions
### Linear Kernel
- represents the standard dot product
- doesn't map the data to a higher feature space
$$K(x_i, x_j) = x_i \cdot x_j$$

### Polynomial Kernel
- maps the input features into a higher-dimensional space defined by polynomial combinations of the original features
- allows the SVM to create decision boundaries that are polynomial curves
- can create more complex decision boundarys than the linear kernel
$$K(x_i, x_j) = (x_i \cdot x_j + c)^d$$
- c is a free parameter trading off the influence of higher-order versus lower-order terms,
- d is the degree of the polynomial

### Radial Basis Function (RBF) Kernel / Gaussian Kernel
- maps the input features into an infinite-dimensional space
- popular choice for SVMs because it can handle very complex relationships between the features
$$K(x_i, x_j) = \exp(-\gamma \|x_i - x_j\|^2)$$
- γ is a parameter that defines the spread of the kernel

### Sigmoid Kernel
- related to neural networks
- can be used to model the similarity between data points in a way that resembles the behavior of a multi-layer perceptron with a single hidden layer
$$K(x_i, x_j) = \tanh(\alpha x_i \cdot x_j + c)$$
- α and ccc are kernel parameters

# Multi-class classification

## One-vs-Rest (OvR) / One-vs-All (OvA)
- binary classifier trained for each class (seperating that class from all other classes)
- Prediction: for a new datapoint each classifier predicts if the point belongs to its class. The class with the highest confidence score (distance from the hyperplane) is chosen.
## One-vs-One (OvO)
- binary classifier trained for every possible pair of classes. For a classification problem with N-classes, $\frac{N(N-1)}{2}$ binary classifiers are trained. For training it only uses data points belonging to these 2 classes .
- Prediction: Each of the $\frac{N(N-1)}{2}$ classifiers predicts which of the two classes the data point belongs to. The final class is determined by a voting scheme where each classifier casts a vote, and the class with the most votes is selected


# Pros
- Effective in high dimensional spaces
- Works well when the number of dimensions exceeds the number of samples
- Memory efficient (uses subset of training points = support vectors) for classification
- Versatile with the use of different kernel functions
# Cons
- not suitable for very large datasets due to high computational cost
- The choice of the kernel and the parameters (like C, γ) significantly affect performance.
- Less effective on noisy datasets with overlapping classes.
