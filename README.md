![image](https://github.com/user-attachments/assets/1925920f-2c9f-489c-914b-ce4cdead9893)

# Crater Detection on Planetary Images

This repository contains code for detecting craters on planetary surface images using computer vision techniques. The project leverages Hough Circle Transform and other image processing methods to identify circular features in satellite or planetary images, which are likely to be craters.

## Table of Contents

- [Overview](#overview)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Parameter Optimization](#parameter-optimization)
- [Results Visualization](#results-visualization)
- [License](#license)

## Overview

This project focuses on detecting circular features (craters) in planetary images. It involves the following key steps:

1. **Image Preprocessing**: Converting the image to grayscale, applying a median blur to reduce noise, and preparing the image for further processing.
2. **Crater Detection**: Using Hough Circle Transform (`cv2.HoughCircles`) to detect circular features in the image.
3. **Parameter Optimization**: Iterating over multiple parameter combinations to find the best set of parameters for circle detection.
4. **Visualization**: Displaying detected craters on the image and plotting the crater size distribution (histogram and cumulative distribution).
5. **Edge Detection**: Using Canny edge detection to highlight the edges of potential craters.

## Prerequisites

Before running the code, ensure you have the following dependencies installed:

- Python 3.x
- OpenCV (`cv2`)
- NumPy
- Matplotlib
- PIL (Pillow)

You can install the required dependencies using `pip`:

```bash
pip install opencv-python numpy matplotlib pillow
```

## Installation

1. Clone this repository to your local machine:

   ```bash
   git clone https://github.com/yourusername/crater-detection.git
   cd crater-detection
   ```

2. Install the necessary dependencies using `pip`:

   ```bash
   pip install -r requirements.txt
   ```

## Usage

To run the crater detection pipeline, simply execute the notebook `crater_counter.ipynb`. The notebook will walk you through the steps of:

1. Loading and preprocessing the planetary image.
2. Detecting craters using Hough Circle Transform.
3. Visualizing the results, including the number of detected craters, histogram, and cumulative distribution of crater sizes.
4. Optimizing the parameters for the best circle detection performance.
5. Performing edge detection on the image.

### Example

```python
from PIL import Image
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Load the image
image_path = '/path/to/your/image.png'
image = cv2.imread(image_path)

# Preprocess the image
blurred, gray = preprocess_image(image)

# Detect craters (circles)
circles = hough_circle_detection(blurred, dp=1.2, minDist=30, param1=100, param2=30, minRadius=5, maxRadius=50)

# Plot results
plot_histogram_and_cumulative(circles)
```

## Parameter Optimization

The Hough Circle Transform method is highly sensitive to the parameters. Different parameter combinations (such as `dp`, `minDist`, `param1`, `param2`, `minRadius`, `maxRadius`) are tested to optimize the detection of craters. The notebook iterates over multiple parameter sets to find the best one that maximizes the number of detected craters.

## Results Visualization

The following visualizations are produced as part of the analysis:

- **Detected Craters**: The image with detected circles (craters) drawn on it.
- **Histogram of Crater Diameters**: A log-log scale histogram showing the distribution of crater sizes.
- **Cumulative Distribution of Crater Diameters**: A plot of the cumulative count of craters as a function of their diameter.
- **Hough Transform Space**: A visualization of the Hough Transform voting space for different parameter sets, helping to identify the best set of parameters for crater detection.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

### Notes:

- Replace the URL in the `git clone` command with your actual repository link.
- You can add a `requirements.txt` file to list the Python dependencies, if you want users to install them easily.
- You may want to further expand on the installation and usage sections depending on your target audience.

This README provides users with clear instructions on how to set up and use the project. It’s designed to be easy to follow and offers a good overview of the project's functionality.
