# Preserving Color in Neural Artistic Style Transfer

## Task
Transfer style while preserving colors.

## Main Idea
### Approach I
**Main Idea**:For the style image S, first use color histogram matching algorithm to generate a new style image S' which matches the color histogram of the content image. Then use S' as the style image and perform conventional neural style transfer algorithm with content image C.

**Problem Definition**: The linear transformation algorithm can be defined as: Given a style image x<sub>s</sub>, seek a 3x3 matrix A and a 3x1 vector b so that: b = μ<sub>c</sub>−Aμ<sub>s</sub> and AΣ<sub>S</sub>A<sup>T</sup> = Σ<sub>C</sub> (μ and Σ are mean and covariance of color pixels ). Then the transferred style image x<sub>S'</sub> = Ax<sub>S</sub>+b has the same mean and covariance of the color pixels with the content image.

**Solution**: Let the eigenvalue decomposition of a covariance matrix be Σ = UΛU<sup>T</sup>.Then, we define a matrix square-root as: Σ<sup>1/2</sup> = UΛ<sup>1/2</sup>U<sup>T</sup>. By mathematical derivation, we get A = Σ<sup>1/2</sup>Σ<sup>-1/2</sup>.

### Approach II
Perform style transfer only in the luminance channel, then concatenate generated luminance channel with I and Q channel from the content image.

If there is a substantial mismatch between the luminance histogram of the style and the content image, it can be helpful to match the histogram of the style luminance channel L<sub>S</sub> to that of the content image L<sub>C</sub> before transferring the style. Let μ<sub>S</sub> and μ<sub>C</sub> be the mean luminance of the two images, and σ<sub>S</sub> and σ<sub>C</sub> be their standard deviations. Then each luminance pixel in the style image is updated as: L<sub>S′</sub> = (σ<sub>C</sub>/σ<sub>S</sub>)(L<sub>S</sub>−μ<sub>S</sub>)+μ<sub>C</sub>.

## Results
<img src="images/preserveNT.png" height="400">

## Reference
Gatys, Leon A., et al. "Preserving color in neural artistic style transfer." arXiv preprint arXiv:1606.05897 (2016).
