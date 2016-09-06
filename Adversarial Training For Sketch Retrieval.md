# Adversarial Training For Sketch Retrieval

## Problem Definition
Given a Merchant Mark, find identical or similar Merchant Marks in the dataset. i.e. Merchant Mark sketch retrieval.

## Chanllenges
- Merchant Mark sketches are line drawings so they don't have color or texture information.
- The dataset is small and has no label, so unsupervised method is needed.

## Contributions
The main contribution of this paper is to show that GANs can be used to learn representations suitable for visual sketch.

## Architechure
![](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/MerchantMark.png)

## Algorithm
### Generator
The structure of generator:
![](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/sketchGAN.png)
Their Generator serves the same purpose as GAN or DCGAN, it learns the distribution of data and maps a noise vector z to a faked data sample. 

### Discriminator
When training, their discriminator serves the same purpose as a discriminator in GAN or DCGAN. But when doing retrieval, they turn this discriminator into an encoder by chopping off the last layer and use the feature of last but one layer as the code for an sketch. A special design for sketch GAN is that they use larger filters in lower levels of the discriminator since sketches are highly abstract, lacking of detailed information.

### Retrieval
Given the sketch to be matched, they first extract features for both this sketch and all sketches in the dataset using the discriminator described above. And then use normalized dot product as similarity measure to retrieve the most similar sketch in the data set.

## Conclusions
They compared sketch GAN with another 'thin GAN' which has very small filters, consistent with most of the state-of-the- art natural image recognition networks. They found that sketch GAN are more invariant to rotation, scale and shift.

## TL;DR
This paper tactfully takes advantage of GAN to learn representations for unlabeled images.

## Reference
Creswell A, Bharath A A. Adversarial Training For Sketch Retrieval[J]. arXiv preprint arXiv:1607.02748, 2016.
