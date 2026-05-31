# Canny Edge Detection

A Python implementation of the Canny Edge Detection algorithm using OpenCV and NumPy. This project demonstrates image processing techniques for detecting edges in images through a Jupyter Notebook.

## Table of Contents

- [Overview](#overview)
- [What is Canny Edge Detection](#what-is-canny-edge-detection)
- [Features](#features)
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
- [Algorithm Steps](#algorithm-steps)
- [Parameters](#parameters)
- [Project Structure](#project-structure)
- [Results](#results)
- [Author](#author)

## Overview

This project implements the Canny Edge Detection algorithm, one of the most popular and effective edge detection techniques in computer vision. The implementation processes an image through multiple stages to identify and highlight edges while minimizing noise.

## What is Canny Edge Detection

The Canny Edge Detection algorithm is a multi-stage technique that:
- Reduces noise in the image
- Calculates gradients to find edge strength and direction
- Applies non-maximum suppression to thin edges
- Uses double thresholding and edge tracking to detect final edges

It is widely used in:
- Object detection
- Image segmentation
- Feature extraction
- Medical imaging

## Features

Key Features:
- Converts color images to grayscale for processing
- Implements Canny edge detection with adjustable thresholds
- Visualizes original, grayscale, and edge-detected images
- Uses OpenCV for efficient image processing
- Matplotlib for result visualization

## Requirements

- Python 3.10 or higher
- OpenCV (cv2)
- NumPy
- Matplotlib

## Installation

1. Clone this repository:
```bash
git clone https://github.com/KBarathraj/Canny-Edge-Detection.git
cd Canny-Edge-Detection
```

2. Install required packages:
```bash
pip install opencv-python numpy matplotlib
```

## Usage

1. Prepare your input image (name it `SEC.png` or modify the filename in the notebook)

2. Run the notebook cells sequentially to:
   - Load and display the original image
   - Convert to grayscale
   - Apply Canny edge detection
   - Visualize the results

3. The notebook will generate visualizations showing the original image, grayscale conversion, and detected edges.

## Algorithm Steps

The Canny Edge Detection process follows these steps:

1. Grayscale Conversion: Convert the color image to grayscale to simplify processing
2. Noise Reduction: Apply Gaussian blur (handled internally by OpenCV)
3. Gradient Calculation: Compute image gradients using Sobel operators
4. Non-Maximum Suppression: Thin the edges by suppressing non-maximum values
5. Double Thresholding: Classify edges into strong, weak, and non-edges
6. Edge Tracking: Use hysteresis to finalize edge detection

## Parameters

The implementation uses the following parameters for cv2.Canny():

```python
cv2.Canny(img_gray, threshold1=180, threshold2=200)
```

- threshold1 (180): Lower threshold for edge detection
- threshold2 (200): Upper threshold for edge detection
- Edges with gradients greater than threshold2 are considered strong edges
- Edges with gradients less than threshold1 are discarded
- Edges between thresholds are considered if connected to strong edges

### Adjusting Thresholds

- Lower thresholds result in more edges being detected, including potential noise
- Higher thresholds result in fewer, more prominent edges only

Example threshold adjustments:

```python
# For more edge details
edges = cv2.Canny(img_gray, threshold1=50, threshold2=150)

# For fewer, stronger edges
edges = cv2.Canny(img_gray, threshold1=250, threshold2=300)
```

## Project Structure

```
Canny-Edge-Detection/
├── README.md              # Project documentation
├── CannyEdge.ipynb        # Main implementation notebook
└── SEC.png                # Sample image (user-provided)
```

## Results

The notebook produces visualizations including:

1. Original Image: The input color image
2. Grayscale Image: Converted to single-channel grayscale
3. Edge Detection Map: Binary image highlighting detected edges

## Author

Barathraj K
- Register No: 212224230033
- Slot: T2 - J6

## License

This project is open source and available for educational purposes.

## References

- Canny Edge Detection - Wikipedia: https://en.wikipedia.org/wiki/Canny_edge_detector
- OpenCV Canny Documentation: https://docs.opencv.org/master/da/d22/tutorial_py_canny.html
- J. Canny, "A Computational Approach to Edge Detection", IEEE Transactions on Pattern Analysis and Machine Intelligence, 1986
