## Main Idea

Proposed a framework that:

- generates a realistic image given a sketch
- colorizes a grayscale image to color image

## Architecture

- an encoder-decoder architecture with residual connections
- Input: sketch with/without color control strokes
- Output: generated realistic image that has same resolution with the input sketch
 
![](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/scrabble.png)

## Objective Function
- Per-pixel L2 difference 
- Feature L2 loss
- Adversarial loss 
(encourage the model to generate sharper edges, higher contrast and more realistic color and lighting, see Figure 3)
- Total Variation loss (encourage smoothness in generated images)

L = w_p x L_p + w_f x L_f + w_adv x L_adv + w_tv x L_tv

## Training Process
To address the unstable training of GAN, this papers uses a two-stage training process:

- First Stage: Turn off the adversarial loss (set w_adv to 0) and train the encoder-decoder network with only l2 loss, feature loss and total variation loss for three epochs
- Second Stage: Fine tune the network with feature loss and adversarial loss for sketch-to-image task; Or fine tune the network with feature loss, l2 loss and adversarial loss for colorization task.

## TL;DR
- This paper used adversarial loss as well as perceptual loss(feature loss). It shows that the adversarial loss can generate images with more diverse color and realistic lighting. One question I have is how important is the feature loss ? Since in the Image-to-image translation paper, they only use L1 loss and the adversarial loss.
- The second point is the training scheme. GAN is notorious for its unstable training process. Also, GANs are often trained with low learning rate(1e-4 or lower), with this learning rate, I don't think L2/L1 loss or feature loss can have much influence on the generator. However, by splitting the training process into two stages, this issue might be addressed. Also, training G for several epochs in advance avoids D to be too strong. 

## Reference
Patsorn Sangkloy, Jingwan Lu, et al. Scribbler: Controlling Deep Image Synthesis with Sketch and Color. arXiv preprint arXiv:1612.00835, 2016.


