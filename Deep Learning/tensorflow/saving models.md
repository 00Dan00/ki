
# Saving Models

## Weights
```python
model.save_weights('path')
model.load_weights('path')
```
- only saves weights of the model
- either in HDF5 or TensorFlow checkpoint format
- usually enough for simple scenarios

## Checkpoint
```python
checkpoint = tf.train.Checkpoint(optimizer=model.optimizer, model=model)
checkpoint.save('path')

# later
checkpoint.restore(tf.train.latest_checkpoint('path'))
```
- saves everything that contributes to the model (weights, optimizer state, any other variable)
- TensorFlow checkpoint format
- useful for more complex scenarios (adaptive learning rate, optimizer decay, custom training loops)


## Model
```python
model.save('path')
model.load('path')
```
- high level API (keras)
- saves entire model (architecture, weights, optimizer, loss, metric, state of optimizer, ...)
- either in HDF5 or TensorFlow SavedModel format (default)
## tf.saved_model
- low level API
- saves everything regarding the model and also things like the computational graph and configuration files but not things regarding training / optimizers
- mainly for deployment and exporting models for production