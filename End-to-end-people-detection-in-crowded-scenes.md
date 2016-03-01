# End-to-end people detection in crowded scenes

## Main Idea
Decoding an image into a set of people detections using an end-to-end network with a LSTM layer

## Advantages
- Multiple detections on the same object can be avoided by remebering the previously generated outputs.
- End-to-end system allows joint training of all components via back propagation.

## Architechure
![Architechture](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/lstm_detection.png)
## Algorithm
1. Using GoogleNet to generate a 15\*20\*1024 image feature map;
2. For each cell in a image feature map, use a LSTM controller to predict a set of bounding boxes;
3. Using Hungarian Algorithm to assign a unique candidate to each ground truth. Predicts with high overlap with ground truths, lower rank and low distances are preferred.
4. Calculate loss function based on the matching result.
5. Backpropagate error through the network

## Questions
Don't quite understand the stiching algorithm

## TL;DR
1. Hungarian Algorithm can be used to match object detection candidates with ground truth boxes.
2. LSTM can be used in object detection since:
   - it "remembers" history predictions so it can avoid multiple predictions on a same object
   - it predicts arbitrarily number of objects in an image

## Reference
Stewart R, Andriluka M. End-to-end people detection in crowded scenes[J]. arXiv preprint arXiv:1506.04878, 2015.
