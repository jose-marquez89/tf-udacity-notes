## CNN notes
Two main concepts:
- convolutions
    - you are actually "convuluting" the original image
    - this is done by taking a kernel and centering over a particular pixel
    - the sum of the element wise multiplication of the kernel sized space of the original image and the kernel itself is summed
    - this value takes the place of the original image's center pixel in the convoluted image
- max pooling
    - essentially a downsampling of the image
    - stride is the number of pixels by which the pooling filter is moved across the image

### Color images
- images will have height, width and 3 color layers of depth
- this results in an interpretation of a 3d matrix
- this will be the `input_shape` parameter:
    - `input_shape=(150, 150, 3)`
- filter kernel will be 3d
- operation is the same as grayscale input for convolution
- the depth of the output convoluted image corresponds to the number of filters used
- max pooling on convoluted outputs
    - 

### Different sized
- NN needs fixed size input
- need to resize all images
- this guarantees same size 1d arrays


### Overfitting
- holdout sets can help with this
- you can constrain weights
- you can use a validation test
    - after training epochs have completed the model can use the validation set to see how far off its predictions are
- Every dataset is crooked
- 90% of your work is cleaning up data
- you can look at the training and validation loss as a function of epoch
    - high validation loss coupled with low training loss is an indication that the model is learning/memorizing the training set
    - this can direct you to a more optimal number of training epochs
    - the reason we maintain a separate test and validation is because we tune the model to perform well on both the training and validation sets; the test set is there to keep us honest

### Image Augmentation
- ideally the CNN should see all examples during training
- augmentation applies random transformations to examples
    - this can include rotations and zoom

### Dropout
- randomly turn off some neurons during training
- makes the network more resistant
- this is specified by a probability
- sometime neurons will be turned off and sometimes not

### Overfitting: Other Techniques
- early stopping
    - track the loss on the validation set during training to see where training and validation loss/accuracy begins to diverge
- image augmentation
    - artificially boost the number of images to basically give the model more practice and prevent the model from being able to memorize a single version of the image
- dropout
    - randomly removing a fixed number of neurons during training


### Output layer
- you can use the sigmoid function for the output layer if you're working with a binary classification problem
- if you use sigmoid you need to use binary cross entropy as opposed to sparse categorical



### Misc Vocab
- Batch Size: specifies how many training examples to feed the model before the weights and biases

### Summary
- Resizing needs to be done because the NN expects things to all be the same size
- color images are interpreted as 3D arrays
- we can convolve and pool for each color channel

