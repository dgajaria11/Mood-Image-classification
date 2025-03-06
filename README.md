Description of Experiments


In this project we trained an Artificial Neural Network(ANN) to classify images to 7 different emotions. We experimented with Neural Network Architecture, tuning hyperparameters, and image transformations to improve the models performance


ANN architectures experimented

Started off with only the linear layer which resulted in a 30% accuracy
For the second model then added 3 Convolutional Layers with 32,64, and 128 neurons which bumped the accuracy to 36%
Added Two fully connected layers with 512 neurons and 7 neurons(for each emotion)and also another Convolutional layer with 256 neurons which got us to around 50% accuracy
Our final and best model has a total of 4 convolutional layers and 3 fully connected layers(Batch Normalization, Dropout layer, connecting to 7 class output) - 55% accuracy



Hyperparameters experimented with

Epochs 5 -> 10 -> 30

Batch size 32 -> 64 -> 128

Used Adam Optimizer

Learning rate:  .001->.0005->.0001

Dropout 0.5->0.3



We began with 5 epochs just to confirm our setup was running smoothly, then moved up to 10 epochs to see if a slightly longer training period improved results, and finally decided on 30 epochs to allow the model enough time to learn without getting stuck in overfitting. For batch size, we found 128 gave us some more stable gradients and improvement in model performance unlike the smaller 32.
When trying the Adam optimizer, we played with learning rates of 0.001, 0.0005, and 0.0001, in the end we found 0.0001 gave us the most accuracy, even though it took longer to train the model. We tested dropout values of 0.3 and 0.5 in our fully connected layers, and found that 0.3 gave a good balance of preventing overfitting and good overall performance.

Image transformation experimented with
We tried rotating the images randomly like turning them horizontally for example, and applying then finding ways of cropping, as well as solarization to add some more variation to each of the training batches helping the model get used to different variables like facial angles.
Accuracies obtained
As we played with and ran models, the basic MLP model stayed at around 30% accuracy on the validation set, but after adding more convolutional layers and using new transformations, we were able to get up to around 55% accuracy which was definitely a big improvement.


Description of Best Model


4 Convolutional layers with a batch normalization layer after each one. 
Max Pooling layer which reduced spatial dimensions
A dropout layer (0.3) after the fully connected layers to prevent overfitting
3 FC functions to compress features down with the final layer outputting final predictions
Relu activation function for bring in non-linearity
Used GPU acceleration through colab to increase training speed

Hyperparameters:

Batch size: 128
Optimizer: Adam
Learning rate: 0.0001
Loss function: CrossEntropy
Epochs: 30
Dropout: 0.3










