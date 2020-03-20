# DeepID

# Introduction
The siamese network is a method for training a distance function discriminatively. Its use is popularized in many facial verification models including ones developed by Facebook and Google. The basic idea is to run a deep net on pairs of images describing either matched or unmatched pairs. The same network is run separately for the left and right images, but the loss is computed on the pairs of images rather than a single image. This is done by making use of the "batch" dimension of the input tensor, and computing loss on interleaved batches. If the left image is always the even idx (0, 2, 4, ...) and the right image is always the odd idxs, (1, 3, 5, ...), then the loss is computed on the alternating batches: loss = output[::2] - output[1::2], for instance. By feeding in pairs of images that are either true or false pairs, the output of the networks should try to push similar matching pairs closer to together, while keeping unmatched pairs farther away. 

# Package
Siamese Network for performing training of a Deep Convolutional Network for Face Verification on the Olivetti and LFW Faces datasets.
