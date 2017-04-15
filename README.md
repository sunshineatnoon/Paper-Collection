### Image Classification:
Network in Network [[Paper]](https://arxiv.org/abs/1312.4400) [[Note]](https://github.com/sunshineatnoon/Paper-Collection/blob/master/NIN.md) [[Torch Code]](https://github.com/szagoruyko/cifar.torch/blob/master/models/nin.lua)
   * Lin, Min, Qiang Chen, and Shuicheng Yan. "Network in network." arXiv preprint arXiv:1312.4400 (2013).
   
VGG [[Paper]](https://arxiv.org/abs/1409.1556) [[Note]](https://github.com/sunshineatnoon/Paper-Collection/blob/master/VGG.md) [[Torch Code]](https://github.com/szagoruyko/cifar.torch/blob/master/models/vgg_bn_drop.lua)
   * Simonyan, Karen, and Andrew Zisserman. "Very deep convolutional networks for large-scale image recognition." arXiv preprint arXiv:1409.1556 (2014).

GoogleNet [[Paper]](http://www.cv-foundation.org/openaccess/content_cvpr_2015/papers/Szegedy_Going_Deeper_With_2015_CVPR_paper.pdf) [[Note]](https://github.com/sunshineatnoon/Paper-Collection/blob/master/GoogleNet.md) [[Torch Code]](https://github.com/soumith/inception.torch/blob/master/googlenet.lua)
   * Szegedy, Christian, et al. "Going deeper with convolutions." Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition. 2015.
   
ResNet [[Paper]](https://arxiv.org/pdf/1512.03385.pdf) [[Note]]() [[Torch Code]](https://github.com/facebook/fb.resnet.torch)
   * He, Kaiming, et al. "Deep residual learning for image recognition." Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition. 2016.

### Popular Module
Dropout [[Paper]](http://www.jmlr.org/papers/volume15/srivastava14a.old/source/srivastava14a.pdf) [[Note]](https://github.com/sunshineatnoon/Paper-Collection/blob/master/Dropout.md)
* Srivastava, Nitish, et al. "Dropout: a simple way to prevent neural networks from overfitting." Journal of Machine Learning Research 15.1 (2014): 1929-1958.

Batch Normalization [[Paper]](https://arxiv.org/abs/1502.03167) [[Note]](https://github.com/sunshineatnoon/Paper-Collection/blob/master/BN.md)
* Ioffe S, Szegedy C. Batch normalization: Accelerating deep network training by reducing internal covariate shift[J]. arXiv preprint arXiv:1502.03167, 2015.

### Object Detection in Image:
RCNN [[Paper]](http://arxiv.org/abs/1311.2524) [[Note]](https://github.com/sunshineatnoon/Paper-Collection/blob/master/RCNN.md) [[Code]](https://github.com/rbgirshick/rcnn)
   * Ross Girshick, Jeff Donahue, Trevor Darrell, Jitendra Malik, Rich feature hierarchies for accurate object detection and semantic segmentation 

Spatial pyramid pooling in deep convolutional networks for visual recognition [[Paper]] (http://arxiv.org/abs/1406.4729) [[Note]](https://github.com/sunshineatnoon/Paper-Collection/blob/master/SPPNet.md) [[Code]](https://github.com/ShaoqingRen/SPP_net)
  * He K, Zhang X, Ren S, et al. Spatial pyramid pooling in deep convolutional networks for visual recognition[J]. Pattern Analysis and Machine Intelligence, IEEE Transactions on, 2015, 37(9): 1904-1916.
  
Fast R-CNN [[Paper]] (http://arxiv.org/pdf/1504.08083) [[Note]](https://github.com/sunshineatnoon/Paper-Collection/blob/master/Fast-RCNN.md) [[Code]](https://github.com/rbgirshick/fast-rcnn)
   * Ross Girshick, Fast R-CNN, arXiv:1504.08083.
   
Faster R-CNN, Microsoft Research [[Paper]] (http://arxiv.org/pdf/1506.01497) [[Note]](https://github.com/sunshineatnoon/Paper-Collection/blob/master/Faster%20R-CNN.md) [[Code]](https://github.com/ShaoqingRen/faster_rcnn) [[Python Code]](https://github.com/rbgirshick/py-faster-rcnn)
   * Shaoqing Ren, Kaiming He, Ross Girshick, Jian Sun, Faster R-CNN: Towards Real-Time Object Detection with Region Proposal Networks, arXiv:1506.01497.
   
End-to-end people detection in crowded scenes [[Paper]] (http://arxiv.org/abs/1506.04878)  [[Note]](https://github.com/sunshineatnoon/Paper-Collection/blob/master/End-to-end-people-detection-in-crowded-scenes.md) [[Code]](https://github.com/Russell91/ReInspect)
   * Russell Stewart, Mykhaylo Andriluka, End-to-end people detection in crowded scenes, arXiv:1506.04878.
   
You Only Look Once: Unified, Real-Time Object Detection [[Paper]] (http://arxiv.org/abs/1506.02640) [[Note]](https://github.com/sunshineatnoon/Paper-Collection/blob/master/YOLO.md) [[Code]](http://pjreddie.com/darknet/yolo/)
   * Joseph Redmon, Santosh Divvala, Ross Girshick, Ali Farhadi, You Only Look Once: Unified, Real-Time Object Detection, arXiv:1506.02640

Adaptive Object Detection Using Adjacency and Zoom Prediction [[Paper]] (http://arxiv.org/abs/1512.07711) [[Note]](https://github.com/sunshineatnoon/Paper-Collection/blob/master/AZNet.md)
   * Lu Y, Javidi T, Lazebnik S. Adaptive Object Detection Using Adjacency and Zoom Prediction[J]. arXiv:1512.07711, 2015. 
   
Inside-Outside Net: Detecting Objects in Context with Skip Pooling and Recurrent Neural Networks [[Paper]](http://arxiv.org/abs/1512.04143) [[Note]](https://github.com/sunshineatnoon/Paper-Collection/blob/master/Inside-Outside-Net.md)
   * Sean Bell, C. Lawrence Zitnick, Kavita Bala, Ross Girshick. arXiv:1512.04143, 2015.
   
G-CNN: an Iterative Grid Based Object Detector [[Paper]](http://arxiv.org/abs/1512.07729v1)
   * Mahyar Najibi, Mohammad Rastegari, Larry S. Davis. arXiv:1512.07729, 2015.
   
### Object Detection in Video:
Seq-NMS for Video Object Detection [[Paper]](http://arxiv.org/abs/1602.08465) [[Note]](https://github.com/sunshineatnoon/Paper-Collection/blob/master/Seq-NMS.md)
   * Wei Han, Pooya Khorrami, Tom Le Paine, Prajit Ramachandran, Mohammad Babaeizadeh, Honghui Shi, Jianan Li, Shuicheng Yan, Thomas S. Huang. Seq-NMS for Video Object Detection. arXiv preprint arXiv:1602.08465, 2016

### Image Caption:

Exploring Nearest Neighbor Approaches for Image Captioning [[Paper]](http://arxiv.org/abs/1505.04467)
   * Devlin J, Gupta S, Girshick R, et al. Exploring Nearest Neighbor Approaches for Image Captioning[J]. arXiv preprint arXiv:1505.04467, 2015.

### Image Generations:
Pixel Recurrent Neural Networks [[Paper]](https://arxiv.org/abs/1601.06759) [[Note]](https://github.com/sunshineatnoon/Paper-Collection/blob/master/pixel-rnn.md)
 * van den Oord A, Kalchbrenner N, Kavukcuoglu K. Pixel Recurrent Neural Networks[J]. arXiv preprint arXiv:1601.06759, 2016.

Variational Autoencoder [[Paper]](http://arxiv.org/abs/1312.6114) [[Note]](http://sunshineatnoon.github.io/VAE/)
   * Kingma D P, Welling M. Auto-encoding variational bayes[J]. arXiv preprint arXiv:1312.6114, 2013.

DRAW: A recurrent neural network for image generation [[Paper]](http://arxiv.org/abs/1502.04623) [[Torch Code]](https://github.com/vivanov879/draw) [[Tensorflow Code]](https://github.com/ericjang/draw) [[Note]](https://github.com/sunshineatnoon/Paper-Collection/blob/master/DRAW.md)
   * Gregor K, Danihelka I, Graves A, et al. DRAW: A recurrent neural network for image generation[J]. arXiv preprint arXiv:1502.04623, 2015.

Scribbler: Controlling Deep Image Synthesis with Sketch and Color [[Paper]](https://arxiv.org/pdf/1612.00835v2.pdf) [[Note]](https://github.com/sunshineatnoon/Paper-Collection/blob/master/scribble.md)
   * Patsorn Sangkloy, Jingwan Lu, et al. Scribbler: Controlling Deep Image Synthesis with Sketch and Color. arXiv preprint arXiv:1612.00835, 2016.

Unsupervised Representation Learning with Deep Convolutional Generative Adversarial Networks [[Paper]](http://arxiv.org/abs/1511.06434)
  * Radford A, Metz L, Chintala S. Unsupervised representation learning with deep convolutional generative adversarial networks[J]. arXiv preprint arXiv:1511.06434, 2015.

Improved Techniques for Training GANs [[Paper]](http://arxiv.org/abs/1606.03498)
  * Salimans T, Goodfellow I, Zaremba W, et al. Improved Techniques for Training GANs[J]. arXiv preprint arXiv:1606.03498, 2016.

InfoGAN: Interpretable Representation Learning by Information Maximizing Generative Adversarial Nets[[Paper]](https://arxiv.org/abs/1606.03657)
  * Chen X, Duan Y, Houthooft R, et al. InfoGAN: Interpretable Representation Learning by Information Maximizing Generative Adversarial Nets[J]. arXiv preprint arXiv:1606.03657, 2016.

Image-to-Image Translation with Conditional Adversarial Networks [[Paper]](https://arxiv.org/abs/1611.07004) [[Note]](https://github.com/sunshineatnoon/Paper-Collection/blob/master/pix2pix.md) [[Torch Code]](https://github.com/phillipi/pix2pix) [[Tensorflow Code]](https://github.com/yenchenlin/pix2pix-tensorflow)
  * Isola P, Zhu J Y, Zhou T, et al. Image-to-Image Translation with Conditional Adversarial Networks[J]. arXiv preprint arXiv:1611.07004, 2016.
  
Learning to Generate Images of Outdoor Scenes from Attributes and Semantic Layouts [[Paper]](https://arxiv.org/abs/1612.00215) [[Note]](https://github.com/sunshineatnoon/Paper-Collection/blob/master/AL_CGAN.md)
  * Levent Karacan, Zeynep Akata, Aykut Erdem, Erkut Erdem. Learning to Generate Images of Outdoor Scenes from Attributes and Semantic Layouts [J]. arXiv preprint arXiv:1612.00215, 2016.

Learning to Discover Cross-Domain Relations with Generative Adversarial Networks [[Paper]](https://arxiv.org/abs/1703.05192) [[Note]](https://github.com/sunshineatnoon/Paper-Collection/blob/master/DiscoGAN.md)
* Kim, Taeksoo, et al. "Learning to Discover Cross-Domain Relations with Generative Adversarial Networks." arXiv preprint arXiv:1703.05192 (2017).

### Activation Maximization
Synthesizing the preferred inputs for neurons in neural networks via deep generator networks [[Paper]](https://arxiv.org/abs/1605.09304) [[Note]](https://github.com/sunshineatnoon/Paper-Collection/blob/master/DGN_AM.md)
  * Nguyen A, Dosovitskiy A, Yosinski J, et al. Synthesizing the preferred inputs for neurons in neural networks via deep generator networks[J]. arXiv preprint arXiv:1605.09304, 2016.

### Style Transfer
A neural algorithm of artistic style [[Paper]](http://arxiv.org/abs/1508.06576) [[Note]](https://github.com/sunshineatnoon/Paper-Collection/blob/master/A%20Neural%20Algorithm%20of%20Artistic%20Style.md)
  * Gatys L A, Ecker A S, Bethge M. A neural algorithm of artistic style[J]. arXiv preprint arXiv:1508.06576, 2015.
  
Perceptual losses for real-time style transfer and super-resolution [[Paper]](https://arxiv.org/abs/1603.08155) [[Note]](https://github.com/sunshineatnoon/Paper-Collection/blob/master/Perceptual%20Losses%20Neural%20Style.md)
  * Johnson J, Alahi A, Fei-Fei L. Perceptual losses for real-time style transfer and super-resolution[J]. arXiv preprint arXiv:1603.08155, 2016.
 
### Super Resolution
Texture Enhancement via High-Resolution Style Transfer for Single-Image Super-Resolution [[Paper]](https://arxiv.org/abs/1612.00085) [[Note]](https://github.com/sunshineatnoon/Paper-Collection/blob/master/style_SR.md)
  * Il Jun Ahn, Woo Hyun Nam. Texture Enhancement via High-Resolution Style Transfer for Single-Image Super-Resolution [J]. arXiv preprint arXiv:1612.00085, 2016.


### Others  
Fully convolutional networks for semantic segmentation [[Paper]](https://arxiv.org/abs/1411.4038) [[Note]](https://github.com/sunshineatnoon/Paper-Collection/blob/master/FCN.md)
   * Long J, Shelhamer E, Darrell T. Fully convolutional networks for semantic segmentation[C]//Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition. 2015: 3431-3440.

### Open Courses
* CS231n: Convolutional Neural Networks for Visual Recognition [[Course Page]](http://vision.stanford.edu/teaching/cs231n/index.html)
* CS224d: Deep Learning for Natural Language Processing [[Course Page]](http://cs224d.stanford.edu/index.html)

### Online Books
* [Deep Learning](http://www.deeplearningbook.org) by Ian Goodfellow, Yoshua Bengio and Aaron Courville

### Mathmatics
* Introduction to Probability Models, Sheldon M. Ross

### Clustering
k-means++: The advantages of careful seeding [[Paper]](http://theory.stanford.edu/~sergei/papers/kMeansPP-soda.pdf) [[Note]](https://github.com/sunshineatnoon/Paper-Collection/blob/master/k-means++.md)
   * Arthur D, Vassilvitskii S. k-means++: The advantages of careful seeding[C]//Proceedings of the eighteenth annual ACM-SIAM symposium on Discrete algorithms. Society for Industrial and Applied Mathematics, 2007: 1027-1035.
