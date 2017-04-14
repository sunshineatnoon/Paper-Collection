# Batch Normalization

##  Internal Covariate Shift
### Definition
The change in the distribution of network activations due to the change in networkparameters during training.

### Why is this a problem?
Because the layers need to continuously adapt to the new distribution.

## Batch Normalization
### Basic Idea
Whitening the activation of each layer so that the activation of each layer is always normal distributed, so the next layer don't need to learn new distribution.

### Algorithm
- Training

<img src="https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/BN.png" height="300">

- Testing

Using the mean and variance statistics during training so that each layer's output only depends on its input.


### Explaination
- The `normalize step` (third equation) ensures that the mean and variance of output activations are the same during training.
- The `scale and shift step` (fourth equation) gives Batch Normalization the ability to `undo` the normalization. For instance, if 
<img src="https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/BN2.png" height="25"> Then we can recover the original activations.
- For fully-connected layers, normalization is done in every dimension of **x**, while in convolutional layers, normalization is done in each feature map. That means, there is one pair of *γ<sup>(k)</sup>* and *β<sup>(k)</sup>* for each feature map. This makes activations whithin the same feature map normalized in the same way, with respect to what convolution does. 

## Advantages of Batch Normalization
- Enables higher learning rate: BN helps to amplify small changes into larger and suboptimal changes in activations in gradients as well as stabilize the parameter growth.
- Less careful about initialization
- Eliminate or reduce Dropout

## Reference
Ioffe S, Szegedy C. Batch normalization: Accelerating deep network training by reducing internal covariate shift[J]. arXiv preprint arXiv:1502.03167, 2015.
