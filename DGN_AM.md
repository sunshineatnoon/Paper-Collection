# Synthesizing the preferred inputs for neurons in neural networks via deep generator networks

## Main Idea
Propose a framework to solve activation maximization: transfer feature maps of a pre-trained network (e.g. CaffeNet) to a realistic image.

## Model
![](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/DGN_AM.png)

The model composes of two parts:
- deep generator network pre-trained from [Generating images with perceptual similarity metrics based on deep networks](https://arxiv.org/abs/1602.02644)
- a DNN pre-trained on ImageNet, e.g. CaffeNet, GoogleNet etc

Visualization Process:
Iteratively backpropagate gradients into the input Code (red bar) so that the corresponding neuron in fc8 (red dot) of DNN has maximum activation.

## TL;DR
- A great amount of fine detail and global structure are captured by the DNN even at the last output layer. This is proven by the fact that the reconstructed image from feature maps in fc6 has not only global coherent structure but also fine details.
- DGN_AM reflects the features learned by neurons from the data and can be a good tool to find out what features from each layer capture. 

## Reference
Nguyen A, Dosovitskiy A, Yosinski J, et al. Synthesizing the preferred inputs for neurons in neural networks via deep generator networks[J]. arXiv preprint arXiv:1605.09304, 2016.

