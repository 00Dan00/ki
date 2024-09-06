# Sigmoid
- it maps any input value to a value between 0 and 1
- often used as output layer in binary classification problems 
$$\sigma(x) = \frac{1}{1 + e^{-x}}$$
![[Pasted image 20240629115739.png]]
## Advantages
- non linear
- smooth gradient = differentiable at all points. [[non differentiability at 0]]
- output between 0 and 1 (binary classification and also controlled output space)
## Disadvantages
- Vanishing Gradient problem [[Backpropagation#Vanishing Gradient Problem]]
- non-zero centered [[non zero centered activation functions]]
- exponential computation, which can be computationally expensive compared to simpler activation functions

# Tanh (hyperbolic tangent function)
- maps input x to an output in the range (-1,1)
$$tanh(x) = \frac{e^x - e^{-x}}{e^x + e^{-x}}$$
## Advantages
- zero-centered output. faster convergence, more balanced gradients 
- smooth and differentiable
- non-linear

## Disadvantages
- Vanishing Gradient Problem [[Backpropagation#Vanishing Gradient Problem]]
- Computationally expensive 

# ReLu (Rectified Linear Unit)
- simple and effective
$$\text{ReLU}(x) = \max(0, x)$$
$$

\text{ReLU}(x) = \begin{cases} 
x & \text{if } x \geq 0 \\
0& \text{if } x < 0 
\end{cases}$$
## Advantages
- non-linear
- sparse activation (only inputs > 0 activate neurons)
- unbound Output (x can be larger than 1 which potentially results in higher gradients and faster learning)
- computationally efficient (easy computation of derivative)
- no vanishing gradient problem
## Disadvantages
- Dying ReLu Problem (neurons can "die" during training, meaning they output zero for all inputs and stop learning)
- unbound Output (while unbound output has its advantages it can also lead to exploding gradients => gradients getting exponentially higher, to prevent that techniques like Gradient Clipping [[Backpropagation#Gradient clipping]] can be utilized. )

### Leaky ReLu
$$

\text{Leaky ReLU}(x) = \begin{cases} 
x & \text{if } x \geq 0 \\
\alpha x & \text{if } x < 0 
\end{cases}$$
- where $\alpha$ is a small constant (e.g., 0.01)
- This variant allows a small gradient when x<0x < 0x<0, preventing neurons from dying.

### Parametric ReLU (PReLU)
$$
\text{PReLU}(x) = \begin{cases} 
x & \text{if } x \geq 0 \\
\alpha x & \text{if } x < 0 
\end{cases}
$$
- where $\alpha$ is a learned parameter

### Exponential Linear Unit (ELU)

$$\text{ELU}(x) = \begin{cases} 
x & \text{if } x \geq 0 \\
\alpha (e^x - 1) & \text{if } x < 0 
\end{cases}
$$
where $\alpha$ is a hyperparameter


