# Texture Enhancement via High-Resolution Style Transfer for Single-Image Super-Resolution

## Main Idea
Propose a three-step framework to enhance low-resolution texture into high-resolution texture using style transfer.

## Algorithm
![](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/style_SR.png)

The algorithm mainly composes of three steps:

1. generate an initial HR image from an interpolated LR image via an SISR(Single Image Super Resoltuion) algorithm 
2. generate an HR style image from the initial HR image via down-scaling and tiling
3. Regard the initial HR image as a content image and the HR style image as a style image and combine them via a customized style transfer algorithm. This style transfer algorithm has two main differences compared to common style transfer algorithms: 1) it uses more than 1 layer for content loss calculation 2) it utilizes the initial HR image as an initial estimate for the final HR image, this way the generated image preserves the original structure better and converges faster.

## TL;DR
This paper gives a novel SR by utilizing style transfer algorithm, their generated texture is of good quality. 

The limitations of this paper is obvious. First it only works on pure texture images since gram matrix is a statistical information collected from the whole image; Second the model needs a optimization process so it's slower than feed-forward SR method.

## Reference

Il Jun Ahn, Woo Hyun Nam. Texture Enhancement via High-Resolution Style Transfer for Single-Image Super-Resolution [J]. arXiv preprint arXiv:1612.00085, 2016.
