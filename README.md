# Tesseract OCR & CV2 Reading Order Recovery of Documents
2 / 2

This is an OCR (Optical Character Recognition) project which aims to identify text regions in an input image and segment them into individual lines. The project is implemented in Python using the OpenCV library.

The main script, OCR(), takes an input image as a parameter and performs the following steps:

Reads the input image in grayscale.
Blurs the image using a Gaussian filter.
Thresholds the image using Otsu's method.
Dilates the thresholded image using a rectangular kernel to join nearby text regions.
Detects contours in the dilated image and creates LineSegmentNode objects for each bounding rectangle.
Identifies the hierarchy of line segments based on their spatial relationships (e.g. whether one line is above or to the left of another).
Topologically Sorts the line segments by their width and assigns a unique number to each segment.
Draws bounding boxes and labels for each line segment in the output image.
The script also includes several helper functions, including is_above(), is_left_of(), is_overlapping(), and is_between(), which are used to determine the spatial relationships between line segments.

To use the OCR function, simply call it with the input image filename and the desired parameters for blur, kernel width, and dilation iterations. The output images will be saved to the current directory with suffixes indicating the step in the processing pipeline.

Note that this project is a work in progress and may not produce accurate results for all input images.

The SortByWidthDraw function can also be called to sort the line segments by width and draw them onto the image. For example:
```python
SortByWidthDraw('input_image')
```
Note that the input image must be in the same directory as the Python script, and should be in JPG format. The output images will also be saved in the same directory with the original image name plus the relevant suffix.
