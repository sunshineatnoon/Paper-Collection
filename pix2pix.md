# Image-to-Image Translation with Conditional Adversarial Networks

## Main Idea
Propose a GAN framework with learned loss for general image-to-image translation tasks

## Advantages
- For several image-to-image translation tasks such as: 1) semantic labels -> photo 2) edges -> photo 3) Day -> Night, this paper uses a simple framework and learned loss to tackle all these tasks.
- The generated images are visually plausible  

## Architechure
![Architechture](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/pix2pix.png)
## Generator
Other than using an auto-encoder as most GAN models do, they use a **Unet** as shown above. The difference between Unet and common auto-encoder is that low-level information from early layers of the encoder can be directly passed to last layers of the decoder, thus details of input images can be maintained. Comparison of auto-encoder vs Unet is shown below, Unet is able to generate images including more details.
![](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/unet_autoencoder.png)
## Discriminator
There are many ways to enforce conditions to GAN, including:

- concatenating the condition to the feature maps from the last few layers of the generator
- Train an extra discriminator which discriminates whether the generated images respect the condition like [Pixel-Level Domain Transfer](https://arxiv.org/abs/1603.07442)
- Use another network to train the generator to make sure the condition can be extracted from the generated images as [ss-gan](https://arxiv.org/pdf/1603.05631.pdf)

This paper uses a neat way to attach condition: let both the generator and discriminator observe the condition images. For the generator, the input is the condition image, and stochasticity is obtained by applying dropout at both training and testing stage (thus one drawback of this paper is that the generated images have little stochasticity). For the discriminator, instead of judging whether the generated images are real or fake, the discriminator judges whether a pair of images are (real image + condition) or (fake image + condition).

Another important feature of the discriminator is that it discriminates whether a patch instead of an image is real or fake. This way the network has less parameters so it trains faster. This design is based on the assumption that pixels only depend on pixels within a patch diameter, thus the PatchGAN can also be seen as a type of texture/style loss.

## Objective 
Other than the discriminator loss, the model uses another L1 loss, so that the L1 loss captures low frequencies in images while the discriminator loss focuses on penalizing high frequencies difference. In my own training experience, the L1 loss makes converging much faster than only using the discriminator loss.

## TL;DR
The framework proposed by this paper is really inspiring, especially the Unet architecture and patchGAN loss. 

## Reference
Isola P, Zhu J Y, Zhou T, et al. Image-to-Image Translation with Conditional Adversarial Networks[J]. arXiv preprint arXiv:1611.07004, 2016.


