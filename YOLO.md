# You Only Look Once: Unified, Real-Time Object Detection

## Main Idea
Regards object detection as a regression problem. After dividing an image into an S\*S grid, for each grid, YOLO predicts B bounding boxes, an objectness score and C class probabilities, yeilding S\*S\*(5\*B+C) outputs per image.

## Advantages
- Extreamly fast. The tiny YOLO model can achieve 155 fps, sufficient for real-time application in video;
- Simple and elegant. The whole end-to-end network can be trained via backpropagation and doesn't rely any region proposal methods.

## Architechure
![Architechture](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/YOLO.png)
## Algorithm
The algorithm is noting more than an end-to-end neural network. 
1. For each image, the neural network generates S\*S\*(5\*B+C) outputs. It means that the image is divided into an S\*S grid and for each cell, the network predicts B bounding boxes(4*B coordinates), an objectness score and C class probabilities.
2. Based on these scores, we can decide which cell contains an object(objectness), where it is(bounding box), and which class it belongs to(class probabilities).
3. During training, each predicted bounding box is assigned to the ground truth bounding box with highest IOU and the whole network optimizes the following loss function:
![YOLO LOSS](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/YOLO_loss.png)

## TL;DR
This paper shows that we can solve object detection as a regression problem based on the high-level feature extracted by CNNs.

## Drawbacks
Only one bounding box is predicted for each grid cell, leaving the algorithm vulnerable to detect small objects in flocks.

## Reference
Redmon J, Divvala S, Girshick R, et al. You only look once: Unified, real-time object detection[J]. arXiv preprint arXiv:1506.02640, 2015.
