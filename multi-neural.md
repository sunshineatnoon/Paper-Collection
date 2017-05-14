# A Learned Representation For Artistic Style

## Task
Train a neural network to learn multiple style-transfer.

## Main Idea 
### Network Architecture
The network architecture is the same with [feed forward neural style transfer]() with two modifications: 
1. Change zero-padding to mirror-padding.
2. Change transposed convolution to up-sampling with convolution.
<img src="images/multi-neural/network.png" height="300">

### Conditional Instance Normalization
**Main Idea**: To model a style, it is sufficient to specialize scaling and shifting parameters after normalization to each specific style.

**Instance Normalization**:  Instance normalization normalizes feature maps after each convolution layer as: X<sub>norm</sub> = (X - μ) / σ. Where X is the feature map, μ, σ are mean and covariance of X.

**Conditional Instance Normalization**: Introduce two NxC matrixes parameters: γ, β (*N is the number of styles, C is the channel of feature map X*)  to normalize the feature map X as: X<sub>norm</sub> = γ<sub>s</sub>((X - μ) / σ) + β<sub>s</sub>. γ<sub>s</sub> and β<sub>s</sub> are the s<sup>th</sup> row of γ and β, specialized to scaling and shifting feature map X to match the s<sup>th</sup> style. Show as below:
<img src="images/multi-neural/CIN.png" height="250">

## Results
<img src="images/multi-neural/Result.png" height="400">

## Reference
Dumoulin, Vincent, Jonathon Shlens, and Manjunath Kudlur. "A learned representation for artistic style." (2017).
