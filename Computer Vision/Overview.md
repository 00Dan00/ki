- convolutional neural networks (CNN) are usually used

# Convolutional Classifier
- 2 parts: convolutional base and a dense head
- base: extracts the features (primarily consists of layers performing convolutions but often includes others as well)
- head: determines the class (primarily consists of dense layers and might include layers like dropout)
- goal is to learn:
	- 1. which features to extract (base)
	- which class to predict based on these features (head)
- fine tuning can be done on only the head using the pretrained base

# Feature Extraction
- performed by the base
- consists of 3 basic operations:
	- 1. Filter an image for a particular feature (convolution)
	- 2. Detect that feature wihtin the filtered image (ReLU)
	- 3. Condense the image to enhance the features (maximum pooling)

![[Pasted image 20240212131627.png]]

# Convolutional Layer with ReLU
- Weights are 2D kernels with a certain size (ex: 3x3) 
- they produce a weighted sum of pixel values
![[Pasted image 20240212132204.png]]
- feature Maps are the result of a kernel applied over an image
- The amount of feature maps created is a hyperparameter
- the dimension of the output is based on the kernel size and stride
- ReLU highlights important features and is nonlinear

# Maximum Pooling
- same concept as convolution 
- idea is that a network would carry a lot of unimportant information without a way to get rid of it
- Max pooling takes a patch of activation and replaces them with the maximum activation in that patch
- leads to transitional invariance -> The loss of some positional information 
- The 2 pixels "become " one ![[Pasted image 20240212133618.png]]
# The sliding window
- both convolution and max pooling are performed over a sliding window with a certain size (kernel/pool size) and step width (stride)
- also there is a padding parameter that dictates how the pixels on the edge are to be handled

## Stride
- >1 means we skip over information -> in convolution usually stride is 1 because we want high quality features
- in max pooling stride is usually > 1 (2x2 or 3x3) 
## Padding
- valid: model only stays inside the input
- same: size of output will be the same as input