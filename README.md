# Exp 8: IMAGE SEGMENTATION USING THRESHOLDING TECHNIQUES
# Name: Sowmiya R
# Reg No: 212225040420

## AIM

To segment an image using Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding techniques using Python and OpenCV.

## SOFTWARE REQUIRED

- Python
- OpenCV
- NumPy
- Matplotlib
- Jupyter Notebook
- Anaconda (optional)

## INSTALLATION

Install the required libraries using the following command:

```bash
pip install opencv-contrib-python-headless numpy matplotlib
```

## ALGORITHM

### Step 1: Import Libraries
- Import OpenCV, NumPy, and Matplotlib.

### Step 2: Read the Input Image
- Load the input image using `cv2.imread()`.

### Step 3: Global Thresholding
- Select a fixed threshold value.
- Apply Global Thresholding using `cv2.threshold()`.
- Display the segmented image.

### Step 4: Adaptive Thresholding
- Apply Adaptive Mean Thresholding.
- Apply Adaptive Gaussian Thresholding.
- Calculate threshold values for different local regions.
- Display both segmented images.

### Step 5: Otsu's Thresholding
- Automatically calculate the optimal threshold value.
- Apply Otsu's Thresholding using `cv2.threshold()`.
- Display the segmented image.

### Step 6: Compare the Results
- Observe and compare the results of all three thresholding techniques.

## PROGRAM:
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Step 2: Read the image and convert to grayscale
image = cv2.imread('Mine.jpeg')  # Replace with your image file path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)  # Convert to grayscale

# Original Image
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert from BGR to RGB for display
plt.title("Original Image")
plt.axis('off')

# Step 3: Use Global Thresholding to segment the image
# Apply global thresholding with a threshold value of 127
_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)

# Step 4: Use Adaptive Thresholding to segment the image
# Apply adaptive thresholding using Gaussian method
adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)

# Step 5: Use Otsu's method to segment the image
# Apply Otsu's method for optimal thresholding
_, otsu_thresholded = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)




# Global Thresholding
plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')

# Adaptive Thresholding
plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')

# Otsu's Method
plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')

# Show the plot
plt.tight_layout()
plt.show()
```


## OUTPUT

The following outputs are obtained:

## 1. Original image
<img width="603" height="240" alt="image" src="https://github.com/user-attachments/assets/2dd1d4f8-b921-4e98-a994-225e159d2d4b" />


## 2. Global Thresholding 
<img width="237" height="246" alt="image" src="https://github.com/user-attachments/assets/65bf8677-fa99-46b8-9b55-1e7a907bc9d0" />


## 3. Adaptive Thresholding
<img width="257" height="237" alt="image" src="https://github.com/user-attachments/assets/5d29f57f-15e3-4354-9000-a91c881a72d2" />


## 4. Otsu's Thresholding
<img width="193" height="237" alt="image" src="https://github.com/user-attachments/assets/9ba9d241-31a8-4fc9-84af-dedf34738ee3" />


## RESULT
Thus, image segmentation was successfully performed using Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding techniques using Python and OpenCV. The results of all three techniques were displayed and compared.

