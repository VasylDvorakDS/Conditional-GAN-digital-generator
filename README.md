# Assignment

In this project, the UNet model should be used as the generator, and a separate discriminator model must be created, along with implementing the training algorithm for the entire conditional GAN architecture. We will train this cGAN model on the MNIST dataset containing images of handwritten digits; this dataset is relatively small.

First, it is necessary to modify the UNet architecture so that the model accepts noise—a tensor of size 32×32—and a label (a number from 0 to 9 corresponding to MNIST classes) as input. To do this:

The input tensor dimensions for convolutions should be (input_batch_size, 1, 32, 32).

Inside the forward function, convert the label into a tensor of size 32×32, where each cell contains the label number. Use the view() and repeat() functions for this.

Concatenate the noise and label tensors.

Modify the first UNetBlock so that it accepts a tensor with two channels.

Train the designed generative model on the MNIST dataset containing images of handwritten digits. It can be loaded using standard operations from the torchvision.datasets library.

Train the cGAN so that the model generates realistic digits.

# Conclusion

A conditional generator based on U-Net was built, which takes noise and class labels as input and generates digit images.

The discriminator receives an image and a label concatenated along the channel dimension and learns to distinguish real images from generated ones.

Binary cross-entropy (BCE loss) is used to train both models.

The classic GAN training loop with Adam optimization is implemented for training both the generator and discriminator.

Convenient functions for visualization and data preparation are implemented to work with images.

Input data is normalized from [0,1] to [-1,1] for better convergence.

Conditional labels are expanded to spatial dimensions, allowing generation control by class.

The overall architecture and training follow modern conditional GAN standards.


