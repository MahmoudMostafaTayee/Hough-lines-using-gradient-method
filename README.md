# Hough Lines Detection using Gradient Method

A Python implementation of the Hough Transform for line detection that utilizes image gradients in both x and y directions to efficiently detect edges without iterating through the full range of theta values.

## Features

- Edge detection using Canny algorithm
- Gradient calculation using Sobel operators in both x and y directions
- Efficient Hough Transform implementation using gradient information
- Peak detection in Hough accumulator space
- Line equation extraction and visualization

## How It Works

The algorithm follows these steps:

1. Convert the input image to grayscale
2. Detect edges using Canny edge detection
3. Compute image gradients using Sobel operators
4. Calculate theta values using arctan of gradients
5. Compute rho values using polar line equation
6. Build Hough accumulator space
7. Detect peaks in the accumulator
8. Convert peaks to line equations
9. Visualize detected lines on the original image

## Dependencies

- OpenCV (`cv2`)
- NumPy
- Matplotlib

## Usage

1. Place your input image in the same directory as the script
2. Update the image filename in the script (currently set to `"92f878e2-fff8-448d-bb64-14eb79ef9d8f.jpg"`)
3. Run the script

The script will display:
- The original image
- The Hough accumulator space
- Peaks detected in the accumulator
- The final image with detected lines

## Key Functions

- `CannyandGradients()`: Computes edges and gradients using Canny and Sobel operators
- `Hough()`: Implements the gradient-based Hough Transform
- `houghpeaks()`: Detects peaks in the accumulator space
- `houghlines()`: Converts peaks to line equations

## Advantages

- More efficient than traditional Hough Transform by using gradient information
- Avoids full theta range iteration
- Better edge detection through combined gradient approach

## Example Output

The script generates three plots:
1. Original input image
2. Hough accumulator space with detected peaks
3. Original image with detected lines overlaid

## Notes

- The current implementation uses fixed Canny thresholds (190, 200) - these may need adjustment for different images
- The peak detection threshold (>100) can be modified for different edge sensitivity
- The number of peaks to detect is currently set to 11
