- if an activation function is non zero centered and entire positive or negative (like sigmoid), then this leads to the gradients also being entire positive or negative. 
- This makes the gradients biased and non balanced gradients. 
- The result of this can be an Oscillatory Behavior because the weight updates can be consistently in the same direction
- This can cause the weights to overshoot the optimal value, as the updates are too large in a particular direction. Because of that the weights might swing back and forth around the optimal value, creating a zig-zag pattern in their updates.
- This can slow down the convergence of the training process or might even lead to suboptimal performance 

## Mitigation strategies
- Gradient Clipping: involves setting a threshold to limit the magnitude of gradients. Can prevent the updates from being too large and causing oscillations.
- Adaptive Learning rate: Using optimization algorithms with adaptive learning rates (e.g., Adam, RMSprop) can help adjust the learning rate dynamically during training. These algorithms can reduce the learning rate when oscillations are detected. 