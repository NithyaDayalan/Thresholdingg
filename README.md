## THRESHOLDING
### Aim :
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

### Software Required :
1. Anaconda - Python 3.7
2. OpenCV

### Algorithm :
#### Step1 :
Load the image and convert it to grayscale.
#### Step2 :
Apply a single, fixed threshold value across the entire image.
#### Step3 :
Calculate and apply a separate, local threshold for different small regions.
#### Step4 :
Calculate and apply a separate, local threshold for different small regions.
#### Step5 :
Show the original image and the three segmented (binary) results for comparison.

### Program :
#### Load the necessary packages
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
#### Read the Image and convert to grayscale
```
image = cv2.imread('exp8img.jpg')  
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert from BGR to RGB for display
plt.title("Original Image")
plt.axis('off')
```
#### Use Global thresholding to segment the image
```
_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)
```
#### Use Adaptive thresholding to segment the image
```
adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)
```
#### Use Otsu's method to segment the image 
```
_, otsu_thresholded = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)
```
#### Display the results
```
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
### Output :
#### Original Image
<img width="680" height="269" alt="image" src="https://github.com/user-attachments/assets/52329e64-46b9-45dd-b6ab-8b2d31e8cf9b" />

#### Global Thresholding
<img width="443" height="291" alt="image" src="https://github.com/user-attachments/assets/8179501c-2151-4fca-b58b-56cf038b9108" />

#### Adaptive Thresholding
<img width="397" height="293" alt="image" src="https://github.com/user-attachments/assets/19414162-3219-44aa-90c7-55ca3af11c4d" />

#### Optimum Global Thesholding using Otsu's Method
<img width="389" height="291" alt="image" src="https://github.com/user-attachments/assets/26d38a85-d064-434d-bb07-77ce363184c5" />

### Result :
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
