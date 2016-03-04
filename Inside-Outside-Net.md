# Inside-Outside Net: Detecting Objects in Context with Skip Pooling and Recurrent Neural Networks

## Main Idea
Use skip-layer and IRNN to introduce scale variants and context information into object detection.

## Advantages
- Large improvements in detecting small object

## Architechure

![Architechture](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/ION.png)

## Algorithm
1. The basic architecture is fast RCNN based on VGG net, with skip layers and IRNN layer explained below;
2. Two ReLU RNN(IRNN) layers lay on top of conv5, with 4 IRNNs in each layer. Each IRNN slides from left-right, right-left, up-down, down-up respectively and generates 4 feature maps. These feature maps include context information. For instance, the left-right feature map includes left contextual information about each cell;

![IRNN](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/IRNN.png)
3. Skip layer extracts a fix-length descriptor from several layers and then L2-normalize, concatenate, rescale, dimension-reduce these descriptor to produce a 512\*7\*7 feature descriptor per proposal.


## Questions
Don't quite how IRNN works and implemented

## TL;DR
1. Feature descriptor from early layers helps dealing with scale variant problem.
2. Context information is critical in detecting small objects and RNNs can be utilized to collect that information.

## Reference
Sean Bell, C. Lawrence Zitnick, Kavita Bala, Ross Girshick. arXiv:1512.04143, 2015.
