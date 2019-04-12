# find_the_nuclei

Hellow! This is a academic activity to show how to use Keras to segmentate nuclei images for biomedical purposes.

The dataset used here belongs to a [2018 competition](https://www.kaggle.com/c/data-science-bowl-2018).

This dataset contains a large number of segmented nuclei images. The images were acquired under a variety of conditions and vary in the cell type, magnification, and imaging modality (brightfield vs. fluorescence). The dataset is designed to challenge an algorithm's ability to generalize across these variations.

The architecture used is the U-net which is a variant of CNN that allows training with smaller datasets.

![U-arch](https://user-images.githubusercontent.com/47385329/56059334-20357d80-5d64-11e9-8936-de70fc636e11.png)

![U-strategy](https://user-images.githubusercontent.com/47385329/56059589-afdb2c00-5d64-11e9-897b-29ee6838612e.png)
> This tiling strategy is important to apply the network to large images, since otherwise the resolution would be limited by the GPU memory.
