# Going deeper with convolutions

## Inception Module
![Inception](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/Inception.png)

- The basic intution behind GoogleNet is same with Network in Network, i.e, replacing conventional convolution layer to achieve better local abstraction.
- **Why inception?** Inception is based on the idea that an optimal local sparse structure of a convolutional vision network can be approximated and covered by readily available dense components. For instance, in GoogleNet, they use three kinds of layers(1x1, 3x3, 5x5 convolutional layers) to cover "concepts" clusters. Each unit from an earlier layer corresponds to some region of the image. 1x1 convolution is used to cover clusters concentrated in a small region, while 3x3 and 5x5 convolutions in the inception layer are used to cover more spread out clusters.
- **Why 1x1 convolution before 3x3, 5x5 inception?** Because 3x3, 5x5 convolutions are expensive, so 1x1 convolutions are used to reduce dimension while not compressing the information.
- **Some efforts to address gradient vanishing problem** Not only use classifiers after the last layer but also use classifiers in the lower stages.

## Some thoughts: 
When NIN and GoogleNet compare their network with preceeding work, they don't take depth into account. It's hard to say their improved accuracy is from the deeper network or the inception structure. [Here](https://www.youtube.com/watch?v=VxhSouuSZDY) is a video explaining why inception is potentially better than simple convoltion. 

## Reference
Szegedy, Christian, et al. "Going deeper with convolutions." Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition. 2015.
