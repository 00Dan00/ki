- key algorithm used in Neural Networks .
- used for adjusting weights of connections between neurons in order to minimize the error
- forward pass (data fed into the network until the output layer)
- calculcate error using error functions
- Backward pass (error is propagated backward through the network)
- This process uses Gradient Descent 
# Gradient Descent
- Vector of partial derivatives 
- indicates the direction and magnitude of adjustments needed to minimize the error
- iterative process
- many optimizers utilize Gradient Descent [[Optimizers]]

## Vanishing Gradient Problem
- some activation functions have gradients that can become very small (approach zero) as it moves backwards during training (or very big = exploding gradients problem). This happens because of the multiplication of possibly small gradients (chain rule).
- This can lead to layers learning very slow or not at all 

### Mitigation Strategies
- ReLu for example doesn't suffer as much as activation functions like sigmoid or tanh
- Batch Normalization helps stabilizing and accelerating the training process
- Skip connections allow gradients to bypass certain layers 
- Gradient clipping limits the magnitude of gradients during training which can prevent them from becoming too small (or too big)


