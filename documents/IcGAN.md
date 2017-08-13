## Invertible Conditional GANs for image editing

### Main Idea

 Train an encoder to map a real image into latent representation z and conditional vector y. Then by changing y, and feed changed y and z into a generator, it generates a new image with altered attribute.

<img src="https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/IcGAN/task.png" height="150">

### Training Process
 1. Use the generator of a pre-trained conditional GAN to create a dataset of generated images x and their latent vectors 𝑧.
  2. Train encoder Ez by minimizing a squared reconstruction loss between z and Ez(x).

### Testing Process
 1. Given an image x. Use Ez and Ey to
decompose this image into a conditional representation y and a latent representation z.
 2. Change y to y' to explicitly change some attributes of x.
 3. Feed z along with y' to the generator and generate a new image x' with changed attributes.

<img src="https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/IcGAN/testing.png" height="200">

- Why use an extra encoder with IcGAN ?

 It is a way to decompose the image into explictly conditional vector y and other implicitly factors z. Then by changing y, we can change attributes of this image.
