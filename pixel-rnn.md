# Pixel Recurrent Neural Networks

## Contributions
Use RNN to capture the distribution of natural images so as to generate crisp, varied and globally coherent images, or compelete occluded images.

## Probability Model
Each pixel is determined by three values: R,G,B.
For each pixel, R depends on all the pixels above and left to this pixel, while G depends both on all the pixels above, left to this pixel and R. B depends on all the pixels above, left to this pixel, as well as R and G. To formally define this:
![](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/probability_prnn.png)

## Row LSTM
The Row LSTM model is an extension on multi-dimensional LSTM. To generate a pixel, the R,G,B values of its above three neighbors are fed into LSTM, then LSTM outputs a probability distribution of this pixel value. Thus, pixels are generate row by row. Its context are as follows:

![](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/row_lstm.png)

Thus its can't use all pixels above the target pixel, only a triangular receptive field.

## Diagonal BiLSTM
In order to take advantage of all pixels before the target pixel, the author also proposes Diagonal BiLSTM, which feeds the pixels of above, left and right neighbor into LSTM to generate the target pixel ( In my conprehension, the author feeds the left and above neighbor in the left-to-right scan, while feeds the right and above neighbor in the right-to-left scan). This way the model can take advantage of all pixels before the target pixel as context:

![](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/biLSTM.png)

## Pixel CNN
To speed up the generation process, the author proposes Pixel CNN to avoid sequential generation during training. This way, we can compute features for all pixel positions at once. But the advantage of paralleliza- tion of the PixelCNN over the PixelRNN is only available during training or during evaluating of test images, because during testing, the newly generated pixel has to be used to generate pixels below or left to it.

## Way to Speed Up LSTM
An LSTM layer has an input-to-state component and a recurrent state-to-state component that together determine the four gates inside the LSTM core.
So in the Row LSTM model, we can use convolution to calculate the input-to-sate component for the whole image at once and state-to-state component row by row.
While in the Diagonal BiLSTM, one needs to skew the image first and then do convolutions like the figure below.

![](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/skew.png)

For instance, the red pixel depends on its left and above neighbor, when you skew the image by one offset, its two neighbors are aligned in one column. So at this point, a 2x1 columnwise convolution can be used to calculate the input-to-state component at once. 

## TL;DR
1. RNNs can be used to capture local image patch's pixel distribution. We can see from the generations in the paper, that the generated image lacks of global structure, so I think RNNs are not capable of capture the whole structure of an image. But whithin a small distance, the generated pixel are coherent.
2. Convolution can be utilized to speed up LSTM calculation, especially when used in images.

van den Oord A, Kalchbrenner N, Kavukcuoglu K. Pixel Recurrent Neural Networks[J]. arXiv preprint arXiv:1601.06759, 2016.
