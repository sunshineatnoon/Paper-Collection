# BEGAN: Boundary Equilibrium Generative Adversarial Networks

## Main Idea:
Proposed a new GAN which:
- Use an auto-encoder as a discriminator
- Match auto-encoder loss distribution rather than sample distribution
- Using an equilibrium term to balance generator and discriminator
- With a new method to measure convergence of GAN

## Network Design

<img src="https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/EBGAN/EBGAN.png" height="350">

Two novelties from conventional GAN:
- Use an auto-encoder in Discriminator
- A simpler architecture, with no batch normalization layer, no dropout et al.

## Objective

<img src="https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/EBGAN/objective.png" height="100">

- L(x): This is the image-wise L1 loss bewteen **real** image and its reconstruction by the auto-encoder (Discriminator).
- L(G(z)): This is the image-wise L1 loss bewteen **fake** image and its reconstruction by the auto-encoder (Discriminator). This means the loss of Discriminator is the difference bewteen **auto-encoder losses** of real images and fake images. Thus BEGAN tries to match auto-encoder loss distribution rather than sample distribution. The Discriminator tries to "reconstruct" real images as good as possible while trying to "reconstruct" fake images as bad as possible. This auto-encoder loss can be viewed as a proxy for matching data distribution.
- *L<sub>G</sub>*: The generator loss is the auto-encoder loss of fake images.
- γ: γ is a hyper-parameter that controls image-diversity over image-quality. It's defined as <img src="https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/EBGAN/gamma.png" height="40">. The lower γ is, the worse image diversity is since it forces D to pay more attention to reconstruct real images rather than discriminate fake images.
- *k<sub>t</sub>*: This is a parameter that help to balance Discriminator and Generator. For instance, large L(x) - L(G(z)) is indicates strong generator. Under this condition *k<sub>t+1</sub>* increases so that Discriminator will pay more attention to L(x) while paying less attention to L(G(x)).
- *λ<sub>k</sub>*: This is a hyper-parameter controls change rate of k, can be viewed as k's learning rate.

# Reference
Berthelot, David, Tom Schumm, and Luke Metz. "BEGAN: Boundary Equilibrium Generative Adversarial Networks." arXiv preprint arXiv:1703.10717 (2017).
