# Very deep convolutional networks for large-scale image recognition

## Main Idea
Deep net with small filters outperforms a shallow net with larger filter.

## Reason
1. Small filters lead to more non-linear layers , which makes the decision function more discriminative.
2. Small filters decrease the number of parameters. For instance, two 3x3 convolution layers have a receptive field of 5x5 and 2x(3x3xCxC)=18(CxC) parameters. While an equivalent single 5x5 layer has 1x(5x5xCxC)=25(CxC) parameters. 
