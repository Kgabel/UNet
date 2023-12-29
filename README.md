# UNet

This repository contains the implementation of a U-Net architecture for semantic segmentation of images using convolutional neural networks (CNNs). Semantic segmentation is a computer vision task where the goal is to classify each pixel in an image into a specific class, allowing for detailed understanding and localization of objects within the scene.


The U-Net architecture, introduced by Ronneberger et al. in 2015, has proven to be highly effective for image segmentation tasks. This repository serves as a guide and codebase for building and training a U-Net model for your own semantic segmentation projects.


**Data Loading and Augmentation**
The code includes a custom dataset class, ImageSegmentation, derived from PyTorch's Dataset class. It loads images and corresponding labels from specified directories. It also implements data augmentation techniques, such as random horizontal flipping and random cropping, to enhance the diversity of the training data.

**Convolutional Block**
There is a basic convolutional block, ConvBlockStudent, that consists of a sequence of 2D convolution, ReLU activation, and Batch Normalization layers. The number of convolution layers and downsampling behavior can be configured through parameters.

**U-Net Architecture**
The U-Net architecture, implemented in the UNetStudent class, follows a typical U-Net structure with an encoder and decoder. The encoder downsamples the input image, while the decoder upsamples and fuses information from the encoder. Skip connections are used to concatenate feature maps from the encoder to the corresponding decoder layers. The output layer uses a 3x3 convolution to produce segmentation results with the specified number of classes.

**Evaluation Metric**
The code defines a function, IoU (Intersection over Union), for calculating per-class and mean IoU metrics. It compares predicted and target labels, taking into account an optional ignore index for certain classes.

**Usage**
The code provides default transformations for training and testing images and labels. It sets up a PyTorch DataLoader for loading the dataset and utilizes the U-Net model for semantic segmentation. The model can be trained and evaluated using appropriate functions.
