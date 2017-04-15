# Learning to Discover Cross-Domain Relations with Generative Adversarial Networks

## Task Description
Discover cross-domain relations given unpaired data.

## Main Idea
Couple two GANs together, each of them learn to map image from one domain to its counterpart image in the other domain with a reconstruction loss and a GAN loss.

## Network Design
<img src="https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/DiscoGAN/network.png" height="350">

## Objectives
### Reconstruction Loss
<img src="https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/DiscoGAN/DiscoGAN_recloss.png" height="25">

This loss gaurantees that learned mapping is bijective, thus ensures 1-to-1 mapping. To understand why this is true, consider the image below. Ideally, we want the left car maps to the left face, the right car maps to the right face. If the left car and right car both map to the right face, then this loss will prevent this from happenning because the right face can only map back to one kind of car, leaving the other reconstruction unsatisfied.
<img src="https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/DiscoGAN/DiscoGAN_injective.png" height="200">

### GAN Loss
<img src="https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/DiscoGAN/DiscoGAN_ganloss.png" height="50">

This loss ensures generated images by G_AB look like images in domain B and vice versa.

## GAN Baseline
<img src="https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/DiscoGAN/GAN.png" height="200">

Why this baseline doesn't work: In this baseline, G_BA learns to map A to B with only reconstruction loss. So when two modes in domain A map to a single mode in domain B, G_BA will map back to the average of the two modes in domain A to minimize the reconstruction loss. But in the proposed network, the generation of B has to look like images in domain A (constrained by D_A), so B has to map fakeB to either mode.

## Questions
**How the reconstruction loss leads to meaningful mappings? For instance, why it can map a left face to a left car for instance instead of a right car ?**

My guess is that meaningful mapping is the most "convinient and effortless" mapping. With limited capacity, generators can only learn such kind of mapping. Or this kind of mapping is a easy-reaching local minima during the optimization process. If anyone has an answer to this question, please let me know :-)

# Reference
Kim, Taeksoo, et al. "Learning to Discover Cross-Domain Relations with Generative Adversarial Networks." arXiv preprint arXiv:1703.05192 (2017).
