# Transfer Learning
Transfer learning is the practice of taking advantage of pre-trained networks tuned by experts for our own purposes.

### Big picture
- when you use transfer learning, the part of the model which you don't train will already have your bases covered in terms of the general aspects of images
- what we really train is the deeper layers that learn the specifics of the images on which we train

### What changes
- the last layer of the pretrained network must be changed to match the number of classes in our data
- you have to ensure that you don't change the pre-trained part of the model in the training process
- the model gets trained but only partially; part of it gets 'frozen'
- randomly initialized weights cause the network to make large errors
    - you don't want the already useful weights to be erroneously updated during backpropagation

### Resources
- you can get pre-trained networks that have been stripped of the classification layer from Tensorflow Hub
