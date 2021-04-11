### Processing Images
- Images are flattened into an 1D array with a length of n x n
- ReLU or rectified linear unit helps to solve non-linear problems as an activation function
    - this is a type of activation function
- softmax
    - this function can be used in the output layer
    - provides probabilities for possible output classes


### Training and Testing
- we split the data into train and test to check how well the model has learned to generalize on the problem it has been given
- without a test set, there will be no way to know if the model is overfitting


### Terminology
- optimizer: the optimizer helps to adjust the parameters in the backward pass of the nn based on the loss function
- loss function: this tells us how far off the prediction outputs are from reality
- metrics: in tensorflow and in general, these are the metrics used to measure loss (MSE, RMSE, accuracy, etc)