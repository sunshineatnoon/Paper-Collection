# Fast R-CNN

## Main Idea
Two key ideas are proposed in Fast R-CNN:

1. Use ROI layer to pool region features from image features
2. Use two "heads" in the network, one is a softmax classifier that classify object class, the other is a regression head which predicts bounding box positions.
3. Use multi-task loss for classification and regression respectively.

## Advantages
- Higher detection mAP due to integrated structure and multi-task loss;
- More efficiency in both space and time due to ROI pooling layer.
- Simplified pipeline compared to SPPNet and R-CNN

## Architechure
![Architechture](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/fast-rcnn-arch.png)

## Algorithm
1. Pre-train on ImageNet
2. Extract image feature only once and then use ROI layer to extract features for different region proposals, feed the region features to the last sibling layers for classification and bounding box regression.

## TL;DR
1. ROI can be utilized to extract region features from an image.
2. The paper does mention a maybe better loss function for regression problem:
 ![Loss](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/fast-rcnn-loss.png)
 As I quote from the paper:"When the regression targets are unbounded, training with L2 loss requires significant tuning of learning rates in order to prevent exploding gradients. Above equation eliminates this sensitivity."
3. SVD can be used to compress fully connected layers to speed them up.
4. Not all convolutional layers need to be fine-tuned, for VGG16, only conv3_1 and up layers are necessary to be fine-tuned. This tip can help saving some training time.
5. Deep ConvNets are adept at directly learning scale invariance.

## Drawbacks
Region proposal algorithm -- selective search becomes the time bottleneck.

## Reference
Ross Girshick, Fast R-CNN, arXiv:1504.08083.
