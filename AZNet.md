# Adaptive Object Detection Using Adjacency and Zoom Prediction

## Main Idea
This paper proposes AZ-Net to use a heuristic and adaptive method to generate region proposals for region-based object detection algorithms.

## Advantages
- Has better recall for higher intersection-over-union thresholds, higher recall for smaller numbers of top proposals and for smaller object instances.
- AZ-Net adaptively focuses its computational resources to search for regions that likely contain small objects.

## Architechture
- AZ-Net

  ![AZ-Net](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/ZOOM-Net.png)


## Algorithm

1. The AZ-Net starts with whole image and predicts a zoom indicator which is used to decide whether to further zoom into the region and a set(11) of bounding boxes with confidence scores called adjancency predictions. Bounding boxes with high confidence scores are used as region proposals for object detectors. Regions with high zoom indicator are further divided into 5 sub regions and feed into AZ-Net again.
2. All region proposals are fed into a object detector such as Fast R-CNN.

## TL;DR

The heuristic rules to decide whether a region contains an object can be useful:

"Firstly, the spatial support of the object should mostly lie within the region." (50% and up). "Secondly, the size of the object should be sufficiently small compared to the size of the region."(25% at most).

## Reference
Lu Y, Javidi T, Lazebnik S. Adaptive Object Detection Using Adjacency and Zoom Prediction[J]. arXiv:1512.07711, 2015.
