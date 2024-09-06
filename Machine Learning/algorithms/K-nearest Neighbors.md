- Instance-Based Algorithm, which means it doesn't actually "train" a model but rather memorizes a dataset
- When making a prediction the model computes the distance between the predicted data point and all training data.
- it finds the k-closest points and bases its prediction off that.
- classification: most common class amongst it's k neighbors
- regression: average value of it's k nearest neighbors

# Common distances
- Euclidian Distance
$$\sqrt{\sum_{i=1}^{n} (x_i - y_i)^2}$$

- Manhatten Distance
$$\sum_{i=1}^{n} |x_i - y_i|$$
- Minkowski Distance
$$\left( \sum_{i=1}^{n} |x_i - y_i|^p \right)^{\frac{1}{p}}$$

