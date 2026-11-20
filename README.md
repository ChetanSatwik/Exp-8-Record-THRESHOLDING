# Image Segmentation Using Thresholding Techniques in OpenCV

## Aim

To segment an image using Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding techniques using Python and OpenCV.

The program performs the following operations:

- Global Thresholding
- Adaptive Thresholding
- Otsu's Thresholding

## Software Used

- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- OpenCV (cv2)
- NumPy
- Matplotlib

## Algorithm

### Step 1:

Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:

Load the input image using OpenCV.

### Step 3:

Convert the input image into grayscale format.

### Step 4: Global Thresholding

- Select a fixed threshold value.
- Apply thresholding to separate foreground and background pixels.
- Display the thresholded image.

### Step 5: Adaptive Thresholding

- Compute threshold values for small regions of the image.
- Apply Adaptive Mean Thresholding.
- Apply Adaptive Gaussian Thresholding.
- Display the segmented images.

### Step 6: Otsu's Thresholding

- Automatically determine the optimal threshold value.
- Apply Otsu's thresholding technique.
- Display the segmented image.

### Step 7:

Compare the results obtained from Global, Adaptive, and Otsu's thresholding methods.

## Program
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('1sample.png')

gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Original Image")
plt.axis('off')

_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)

adaptive_thresholded = cv2.adaptiveThreshold(
    gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
    cv2.THRESH_BINARY, 11, 2
)

_, otsu_thresholded = cv2.threshold(
    gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU
)

plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')

plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')

plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')

plt.tight_layout()
plt.show()
```

## Output


<img width="145" height="209" alt="download" src="https://github.com/user-attachments/assets/e455ce3b-24df-4943-b65f-37e4c416ff30" /><br>


<img width="488" height="470" alt="download" src="https://github.com/user-attachments/assets/771c0b0f-c310-42cb-8e62-d1a12139248f" /><br>












### Original Grayscale Image

- The grayscale version of the input image is displayed.
- Serves as the input for thresholding operations.

### Global Thresholding

- Original image is displayed.
- Thresholded image is displayed.
- A fixed threshold value is used for segmentation.
- Pixels are classified as foreground or background.

### Adaptive Thresholding

- Original image is displayed.
- Adaptive Mean Thresholded image is displayed.
- Adaptive Gaussian Thresholded image is displayed.
- Threshold values vary across different regions of the image.
- Suitable for images with uneven illumination.

### Otsu's Thresholding

- Original image is displayed.
- Otsu segmented image is displayed.
- Optimal threshold value is calculated automatically.
- Produces improved segmentation for bimodal histograms.


## Result

Thus, image segmentation is successfully performed using **Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding** techniques in OpenCV. 
