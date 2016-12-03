#Learning to Generate Images of Outdoor Scenes from Attributes and Semantic Layouts

## Main Idea
Propose a **conditional generative adversarial network** that generate outdoor scenes conditioning on **semantic layout** and **scene attributes**.

## Pipeline
![](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/la_cgan.png)
* Generator: 5 convolutional layers + 4 deconvolutional layers
* Descriminator: 6 convolutional layers + 1 fully connected layer
* Both G and D see semantic condition and attributes condition

## Key Points
* The descriptive power of a generator can be increased by conditioning it with respect to side information, i.e. semantic map and attributes.
* Different noise can yielding different generation, but from the images in this paper, the variant is tiny.

## Dataset
- [ADE20K](http://groups.csail.mit.edu/vision/datasets/ADE20K/)
- [Transient Attributes Dataset](http://transattr.cs.brown.edu/)

## TL;DR
This paper shows that providing additional side information in the form of conditioning variables is helpful for learning to generate better natural-looking images.

## Reference
Levent Karacan, Zeynep Akata, Aykut Erdem, Erkut Erdem. Learning to Generate Images of Outdoor Scenes from Attributes and Semantic Layouts
[J]. arXiv preprint arXiv:1612.00215, 2016.


