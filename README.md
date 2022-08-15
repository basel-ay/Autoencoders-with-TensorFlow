# Autoencoders-with-TensorFlow

An autoencoder is a type of artificial neural network used to learn efficient codings of unlabeled data.

However, we might want to use raw (unlabeled) data for training CNN feature extractors, which is called self-supervised learning. Instead of labels, we will use training images as both network input and output. The main idea of autoencoder is that we will have an encoder network that converts input image into some latent space (normally it is just a vector of some smaller size), then the decoder network, whose goal would be to reconstruct the original image.

![image](https://user-images.githubusercontent.com/64821137/184560831-35c5cb15-27a5-481e-b449-a6ca6ec46ebd.png)

Since we are training an autoencoder to capture as much of the information from the original image as possible for accurate reconstruction, the network tries to find the best embedding of input images to capture the meaning.

## Scenarios for using Autoencoders

* `Lowering the dimension of images for visualization or training image embeddings.` Usually autoencoders give better results than PCA, because it takes into account spatial nature of images and hierarchical features.

* `Denoising,` i.e. removing noise from the image. Because noise carries out a lot of useless information, autoencoder cannot fit it all into relatively small latent space, and thus it captures only important part of the image. When training denoisers, we start with original images, and use images with artificially added noise as input for autoencoder.

* `Super-resolution, increasing image resolution.` We start with high-resolution images, and use the image with lower resolution as the autoencoder input.

* `Generative models.` Once we train the autoencoder, the decoder part can be used to create new objects starting from random latent vectors.
