### CNN notes
Two main concepts:
- convolutions
    - you are actually "convuluting" the original image
    - this is done by taking a kernel and centering over a particular pixel
    - the sum of the element wise multiplication of the kernel sized space of the original image and the kernel itself is summed
    - this value takes the place of the original image's center pixel in the convoluted image
- max pooling
    - essentially a downsampling of the image
    - stride is the number of pixels by which the pooling filter is moved across the image