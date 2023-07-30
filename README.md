# Image Compression using PCA with OpenCV

# Overview

This repository contains the code and resources for a project focused on image compression using OpenCV and Principal Component Analysis (PCA). The aim of this project is to demonstrate how PCA can be utilized for reducing the dimensionality of images while preserving essential information, thus achieving efficient image compression. This README provides detailed information on the project, its contents, dependencies, usage, and more.

# This project implements an image compression technique using Principal Component Analysis (PCA) in OpenCV. The key steps are:

1. Read input image
2. Convert to grayscale if image is RGB  
3. Flatten image into single column vector
4. Calculate covariance matrix from image data
5. Compute eigenvectors and eigenvalues of covariance matrix
6. Sort eigenvectors by decreasing eigenvalues
7. Choose k principal components with largest eigenvalues
8. Project image data onto principal components to get new feature vector 
9. Compute compressed image from feature vector and principal components
10. Optionally quantize feature vector for increased compression 
11. Calculate compression ratio and visualize results

# PCA is used for dimensionality reduction by projecting the original high-dimensional data onto a lower-dimensional space defined by the principal components. This removes redundant data and allows the important structure of the image to be captured in fewer components.

# For image compression, we retain only the components with the largest eigenvalues, as these contain the most information about the image. The remaining components are discarded, resulting in a compressed representation of the image.


# Dependencies

- OpenCV 4.x
- NumPy
- Matplotlib (for visualization)


# Usage

The main compression script is `Image_compression_using_Open_cv_and_PCA_.ipynb`.  

# Run it as: 

```
python Image_compression_using_Open_cv_and_PCA_.ipynb --image <input_image> [--num_components <k>] [--quantize]  
 ```

# This will:

- Load image and convert to grayscale if needed
- Calculate PCA and retain k principal components
- Project image onto PCA space 
- Reconstruct compressed image
- Calculate compression ratio
- Visualize original, PCA reconstruction, and quantized (if enabled)

# The key parameters are:

- `--image`: Input image path
- `--num_components`: Number of principal components to retain (k). More components preserves more information but is less compressed. Default is 150.  
- `--quantize`: Enable quantization of the feature vector. This further compresses the image but loses more information.


# Implementation Details

# The core PCA algorithm is implemented in `pca.py`. It contains functions to:

- Calculate covariance matrix
- Compute PCA with SVD
- Project points onto PCA space  
- Reconstruct points from PCA space

The main `Image_compression_using_Open_cv_and_PCA_.ipynb` script ties all the components together.

Using quantization further compresses the images but loses more visual quality.


# Future Work

# Some ideas for extending this project:

- Compare PCA performance to other compression algorithms like JPEG
- Optimize parameters like number of components for best visual quality  
- Implement incremental PCA for processing video
- Experiment with different quantization schemes
- Add support for compressing color images


# References

- Jolliffe, I. T. (2002). Principal Component Analysis. Springer. 
- opencv.org. (2021). OpenCV: Principal Component Analysis. https://docs.opencv.org/4.x/d1/dee/tutorial_introduction_to_pca.html


# Contact

- umairh1819@gmail.com

 
