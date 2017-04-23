# Show and Tell: A Neural Image Caption Generator

## Task
Image Captioning: Generate natural sentences describing an image.

## Network Design
<img src="https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/showandtell/showandtell.png" height="400">

- CNN: GoogleNet, use the last hidden layer to represent an image and input to the LSTM to generate sentence. **Image features only shown at the first time step of LSTM, otherwise, the model will be more prone to overfit.**
- LSTM: Used to generate word based on image features and previously generated words:<img src="https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/showandtell/eq.png" height="75">

## Objective
Sum of the negative log likelihood of the correct word at each step:

<img src="https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/showandtell/objective.png" height="75">

## Training Details
- Use pre-trained GoogleNet to initialize CNN and fix its weights during training.
- Change parameters of embedding layer and LSTM during training.

## Reference
Vinyals, Oriol, et al. "Show and tell: A neural image caption generator." Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition. 2015.
