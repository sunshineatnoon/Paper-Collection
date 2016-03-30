# Seq-NMS for Video Object Detection

## Main Idea
Use Faster R-CNN as single frame object detector and a dynamic programing algorithm to boost weak detections of each frame within a video clip.

## Advantages
- Superior performance to single frame detectors

## Architechture
- Seq-NMS Algorithm

  ![Seq-NMS](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/seq-nms.png)

- Sequence Selection Algorithm

  ![Seq-Selection](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/seq-selection.png)

## Algorithm

The algorithm has three steps: Sequence Selection, Sequence Rescoring and Suppression.
- Sequence Selection: When two bounding boxes from adjacent frames have an IOU above a threshold, they are linked. Sequence Selection algorithm use dynamic programming to find a sequence of linked bounding boxes within a clip that has highest score sum.
- Sequence Re-scoring: Sequence Rescoring algorithm assign new scores to each linked bounding box based on the scores of bounding boxes in the sequence. Average or max is adopted in this paper.
- Suppuression: Bounding boxes in the same frame that have IOU exceeding some threshold are supressed.
Above three steps comprise an iteration, after an iteration, the selected sequence along with suppressed bounding boxes in the last step are removed.
The iteration repeats until no sequences are left.

## TL;DR

Object detection in video can take advantage of temporal consistency to boost detections from adjacent frames.

## Reference
Wei Han, Pooya Khorrami, Tom Le Paine, Prajit Ramachandran, Mohammad Babaeizadeh, Honghui Shi, Jianan Li, Shuicheng Yan, Thomas S. Huang. Seq-NMS for Video Object Detection. arXiv preprint arXiv:1602.08465, 2016
