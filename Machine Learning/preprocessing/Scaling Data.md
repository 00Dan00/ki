# When to use which scaler
## Standard Scaler
- data follows a Gaussian (normal) distribution
- algorithms that assume normally distributed data (Linear Regression, Logistic Regression, SVM, K-clustering)
- You want to standardize features to have zero mean and unit variance
## MinMax Scaler
- You need to scale features to a specific range, typically 0, 1 or -1, 1
- Your data does not necessarily follow a Gaussian distribution
- You are using algorithms that are sensitive to the range of the data, such as: Neural Networks, Gradient-based algorithms
## MaxAbs Scaler
- You have sparse data (e.g., text data represented as word frequencies or TF-IDF scores)
- You want to maintain the sparsity of the data.
- You need to preserve the sign of the data (i.e., keep positive and negative values).
## Robust Scaler
- when the data contains outliers
- You want to scale features without being influenced by outliers
- You are using algorithms that are sensitive to the range of the data but robust to outliers, such as Tree-based-models

# Standard Scaler 
- - Given a dataset X with n samples and m features, let $X_{ij}$ denote the value of the j-th feature of the i-th sample. The standardized value $Z_{ij}$​ of $X_{ij}$​ is given by: 


$$Z_{ij} = \frac{X_{ij} - \mu_j}{\sigma_j}$$
Where the mean is:

$$\mu_j = \frac{1}{n} \sum_{i=1}^{n} X_{ij}$$

and the standard deviation is:
$$\sigma_j = \sqrt{\frac{1}{n} \sum_{i=1}^{n} (X_{ij} - \mu_j)^2}$$
## Example
$$Input:\begin{pmatrix} 1 & 2 \\ 3 & 4 \\ 5 & 6 \\ \end{pmatrix}$$

$$\text{mean}_1 = \frac{1+3+5}{3} = 3, \quad \text{mean}_2 = \frac{2+4+6}{3} = 4$$
$$\text{std}_1 = \sqrt{\frac{(1-3)^2 + (3-3)^2 + (5-3)^2}{3}} = 2, \quad \text{std}_2 = \sqrt{\frac{(2-4)^2 + (4-4)^2 + (6-4)^2}{3}} = 2$$
$$column1:1 - 3 = -1, \quad 3 - 3 = 0, \quad 5 - 3 = 1$$
$$column2:2 - 4 = -1, \quad 4 - 4 = 0, \quad 6 - 4 = 1$$
$$result:
\begin{array}{cc}
-1 & -1 \\
0 & 0 \\
1 & 1 \\
\end{array}$$

# MinMax Scaler
$$X_{\text{scaled}} = \frac{{X - X_{\text{min}}}}{{X_{\text{max}} - X_{\text{min}}}}$$
## Example
$$Input:\begin{pmatrix} 1 & 2 \\ 3 & 4 \\ 5 & 6 \\ \end{pmatrix}$$
$$X_{\text{min}} = \begin{pmatrix} 1 & 2 \end{pmatrix}, \quad X_{\text{max}} = \begin{pmatrix} 5 & 6 \end{pmatrix}$$
$$X_{\text{scaled}} = \frac{{\begin{pmatrix} 1 & 2 \\ 3 & 4 \\ 5 & 6 \end{pmatrix} - \begin{pmatrix} 1 & 2 \\ 1 & 2 \\ 1 & 2 \end{pmatrix}}}{{\begin{pmatrix} 5 & 6 \\ 5 & 6 \\ 5 & 6 \end{pmatrix} - \begin{pmatrix} 1 & 2 \\ 1 & 2 \\ 1 & 2 \end{pmatrix}}}$$
$$= \frac{{\begin{pmatrix} 0 & 0 \\ 2 & 2 \\ 4 & 4 \end{pmatrix}}}{{\begin{pmatrix} 4 & 4 \\ 4 & 4 \\ 4 & 4 \end{pmatrix}}}$$
$$= \begin{pmatrix} 0 & 0 \\ 0.5 & 0.5 \\ 1 & 1 \end{pmatrix}$$
# MaxAbs Scaler
$$X_{\text{scaled}} = \frac{X}{X_{\text{maxabs}}}$$
## Example
$$Input:\begin{pmatrix} 1 & 2 \\ 2 & 4 \\ 5 & 6 \\ \end{pmatrix}$$
$$X_{\text{maxabs}} = \begin{pmatrix} 5 & 6 \end{pmatrix}$$
$$X_{\text{scaled}} = \begin{pmatrix} \frac{1}{5} & \frac{2}{6} \\ \frac{2}{5} & \frac{4}{6} \\ \frac{5}{5} & \frac{6}{6} \\ \end{pmatrix}$$
$$X_{\text{scaled}} = \begin{pmatrix} 0.2 & 0.333 \\ 0.4 & 0.667 \\ 1 & 1 \\ \end{pmatrix}$$

# Robust Scaler
$$X_{\text{scaled}} = \frac{X - \text{median}(X)}{\text{IQR}(X)}$$
$$\text{median}(X) = \text{median of each feature}$$
$$\text{IQR}(X) = \text{Q3} - \text{Q1} \ (\text{interquartile range of each feature})$$
## Example
$$X = \begin{pmatrix} 1 & 2 \\ 2 & 4 \\ 5 & 6 \\ \end{pmatrix}$$
$$\text{median}(X) = \begin{pmatrix} 2 & 4 \end{pmatrix}$$
$$\text{IQR}(X) = \begin{pmatrix} 5 - 1 & 6 - 2 \end{pmatrix} = \begin{pmatrix} 4 & 4 \end{pmatrix}$$
$$X_{\text{scaled}} = \frac{\begin{pmatrix} 1 & 2 \\ 2 & 4 \\ 5 & 6 \end{pmatrix} - \begin{pmatrix} 2 & 4 \\ 2 & 4 \\ 2 & 4 \end{pmatrix}}{\begin{pmatrix} 4 & 4 \\ 4 & 4 \\ 4 & 4 \end{pmatrix}}$$
$$= \frac{\begin{pmatrix} -1 & -2 \\ 0 & 0 \\ 3 & 2 \end{pmatrix}}{\begin{pmatrix} 4 & 4 \\ 4 & 4 \\ 4 & 4 \end{pmatrix}}$$
$$= \begin{pmatrix} -0.25 & -0.5 \\ 0 & 0 \\ 0.75 & 0.5 \end{pmatrix}$$
