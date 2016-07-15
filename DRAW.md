# DRAW: A recurrent neural network for image generation

## Main Idea
Combine RNN and the attention mechanism into variational autoencoder to generate images.

## Architechture

  ![DRAW](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/DRAW.png)

## Algorithm

### Whole Algorithm:
For each time step:
  1. Suppose x is the input image, first use read in attention mechanism to choose which patch of the image should be input into the **Encoder RNN**.
     
     ![](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/DRAW/1.png)
  2. The Encoder RNN emits hidden state h_enc
     
     ![](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/DRAW/2.png)
  3. Use h_enc to generate parameters of distribution Q(z) ~ N(z|mu,sigma) ans sample z:
     
     ![z param](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/z_param.png)
     
     ![z param](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/DRAW/3.png)
  4. Input sampled z into the **Decoder RNN** to get h_dec
     
     ![](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/DRAW/4.png)
  5. Input h_dec into write in attention mechanism and add output to the canvas c_t.
     
     ![](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/DRAW/5.png)
  6. Use the canvas from the last time step T to generate paramters of the distribution of pixels: D(x|c_T), here this distribution is Bernoulli, so sigmoid(c_T) is the mean of this distribution.
  
### Read and Write Attention Mechanism:
#### Read and Write without attention

In this case, the input is just the whole image, and the output of the Decoder RNN modifies the whole canvas at each time step.

![](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/DRAW/6.png)

#### Selective Attention Model
In this case, the author impose a N*N grid of Gaussian filters on top of the image, and get parameters of these Gaussian filters from the hidden state of the Decoder RNN:
Then use these Gaussian filters to choose which part of the image being input into the Encoder RNN and which part of canvas is modified.
1. Generate paramters of the Gaussian filters:

  ![](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/DRAW/7.png)
  ![](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/DRAW/11.png)
  
2. Then the Gaussian filters can be written as:

  ![](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/DRAW/8.png)
  
3. Thus, we have read and write equations like this:

  ![](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/DRAW/9.png)
  ![](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/DRAW/10.png)
  
### Loss function
The Loss function is the same as Variational Autoencoder. It also consists of two parts: the reconstruction error and the regularization error.

#### Regularization Error
Assuming z~N(0,1), then the regularization error is the same as the one in VAE:

![](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/DRAW/12.png)

#### Reconstruction Error
The reconstruction error is the negative log probability of x under Bernoulli distribution, whose mean is given by sigmoid(c_T):

![](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/DRAW/13.png)

## Reference
Gregor K, Danihelka I, Graves A, et al. DRAW: A recurrent neural network for image generation[J]. arXiv preprint arXiv:1502.04623, 2015.
