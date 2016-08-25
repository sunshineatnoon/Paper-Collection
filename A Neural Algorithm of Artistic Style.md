# A Neural Algorithm of Artistic Style

## Main Idea
Representations of content and style of an image in the Convolutional Neural Network are separable. So we can transfer the style of image A to image B, while keeping contents in image B.

## Architechure
VGG Net

## Algorithm
The basic architecture of the CNN used in the algorithm is a VGG net. Training samples contain pairs of painting and photograph. The synthesized image has to capture the contents of the photograph as well as the style of the painting. Thus we have to learn content representations from the photograph and style representations from the painting:

1. Learning contents repesentations is straight forward. We first randomly generate a white noise image, then we change the white noise image through back propagation util it generates the same feature maps in a certain layer of VGG as the original image.(Note that we only change pixels in the white noise image, but keep the weights of VGG fixed).
2. Style representation is computed as the correlation between different feature maps. It is captured by  [Gram Matrix](https://en.wikipedia.org/wiki/Gramian_matrix). Say for layer l, the correlation between feature map i and feature map j is an entry at (i,j) of the Gram Matrix. It can be calculated as the equation below, F_l in the equation indicates the feature maps at layer l. 
    ![](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/NeuralSytle.png)
    
    To understand why Gram Matrix captures style representation, we can view the C\*H\*W feature map as a H\*W grid, and each node on this grid is described by a C-dimensional feature vector. Then the gram maxtrix captures which features are likely to co-occur, i.e. the style of this image. For instance, in the famous "The Starry Night" of van Gogh, blue and yellow co-occur a lot. By capturing this style ,we can see that in the synthesized image, blue and yellow co-occurs a lot too.(Of course, these are pretty high level features.)
![](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/van%20gao.png)
3. To generate an image mixed with the content of a photograph as well as the style of a painting, we just jointly minimise the distance of a white noise image from the content representation of the photograph in one layer of the network and the style representation of the painting in a number of layers of the CNN. So the total loss is:
    ![](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/NueralStyleLoss.png)
   p is for photograph, a is for painting and x is for the randomly generated white noise image. Alpha and Beta controls the balance between style and content. With high Alpha and low Beta, the generated image will maintain most contents in the photo graph, but renders less style of the painting, and vise versa. 

## TL;DR
1. Content and style can be both captured by CNNs, and they are separable.
2. Content can be captured by feature maps in CNNs while style can be captured by correlations between feature maps in CNNs.

## Reference
Gatys L A, Ecker A S, Bethge M. A neural algorithm of artistic style[J]. arXiv preprint arXiv:1508.06576, 2015.
