# find_the_nuclei

Hellow! This is an academic activity to show how to use Keras to segmentate nuclei images for biomedical purposes.

The dataset used here belongs to a [2018 competition](https://www.kaggle.com/c/data-science-bowl-2018).

This dataset contains a large number of segmented nuclei images. The images were acquired under a variety of conditions and vary in the cell type, magnification, and imaging modality (brightfield vs. fluorescence). The dataset is designed to challenge an algorithm's ability to generalize across these variations.

The architecture used is the U-net which is a variant of CNN that allows training with smaller datasets.

![U-arch](https://user-images.githubusercontent.com/47385329/56059334-20357d80-5d64-11e9-8936-de70fc636e11.png)

![U-strategy](https://user-images.githubusercontent.com/47385329/56059589-afdb2c00-5d64-11e9-897b-29ee6838612e.png)
> This tiling strategy is important to apply the network to large images, since otherwise the resolution would be limited by the GPU memory.

## Network architecture
> The network architecture is illustrated in Figure 1. It consists of a contracting path (left side) and an expansive path (right side). The contracting path follows the typical architecture of a convolutional network. It consists of the repeated application of two 3x3 convolutions (unpadded convolutions), each followed by a rectified linear unit (ReLU) and a 2x2 max pooling operation with stride 2 for downsampling. At each downsampling step we double the number of feature channels. Every step in the expansive path consists of an upsampling of the feature map followed by a 2x2 convolution (“up-convolution”) that halves the number of feature channels, a concatenation with the correspondingly cropped feature map from the contracting path, and two 3x3 convolutions, each fol- lowed by a ReLU. The cropping is necessary due to the loss of border pixels in every convolution. At the final layer a 1x1 convolution is used to map each 64-component feature vector to the desired number of classes. In total the network has 23 convolutional layers.

> To allow a seamless tiling of the output segmentation map (see Figure 2), it is important to select the input tile size such that all 2x2 max-pooling operations are applied to a layer with an even x- and y-size.

## Source: 
[U-Net: Convolutional Networks for Biomedical Image Segmentation](https://arxiv.org/abs/1505.04597)
