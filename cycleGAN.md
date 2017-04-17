# Unpaired Image-to-Image Translation using Cycle-Consistent Adversarial Networks

## Task Description
Translate an image from a source domain X to a target domain Y in the absence of paired examples.

## Main Idea
Train mappings G: X -> Y and F: Y -> X  simultaneously with a cycle consistency loss and adversarial loss.

## Network Design
### Generator
[Auto Encoder](https://github.com/jcjohnson/fast-neural-style/blob/master/fast_neural_style/models.lua) from [fast neural-style transfer](http://cs.stanford.edu/people/jcjohns/eccv16/)

Two stride-2 convolutions -> Residual Blocks(6 for 128x128 images and 9 for 256x256 images) -> Two stride-1/2 fractional-stride convolutions

### Discriminator
[PatchGAN](https://github.com/phillipi/pix2pix/blob/master/models.lua) from [pix2pix](https://phillipi.github.io/pix2pix/) which tries to discriminates overlapping 70x70 patches to be real/fake.
Advantages of PatchGAN compared to conventional discriminator:
- Less parameters
- Can be applied to abitrary-sized images

## Objectives
### Cycle Consistency Loss
<img src="https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/CycleGAN/cycleCons.png" height="200">
<img src="https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/CycleGAN/cycleConsEq.png" height="70">
The cycle consistency loss is to prevent the learned mappings G and F from contradicting each other.

### Adversarial Losses
<img src="https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/CycleGAN/GANLoss.png" height="70">
The adversarial loss is to match the distribution of generated images to the data distribution in the target domain;

## Differences from [DiscoGAN](https://arxiv.org/abs/1703.05192)
1. Generator's archetecture
2. Cycle GAN replaces the negative log likelihood objective by a least square loss which is able to stable training and generate images of higher quality.
   
   <img src="https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/CycleGAN/MSE.png" height="70">
3. Cycle GAN uses a history of generated images rather than the ones produced by the latest generative networks and keeps an image buffer that stores the 50 previously generated images.

## Reference
Zhu J Y, Park T, Isola P, et al. Unpaired Image-to-Image Translation using Cycle-Consistent Adversarial Networks[J]. arXiv preprint arXiv:1703.10593, 2017.

