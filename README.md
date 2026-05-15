# EX. NO: 8
# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1: 
Load all the libraries

### Step2: 
Read the image and convert to grayscale

### Step3: 
Use Global Thresholding to segment the image. Apply global thresholding with a threshold value of 127

### Step4: 
Use Adaptive Thresholding to segment the image. Apply adaptive thresholding using Gaussian method

### Step5: 
Use Otsu's method to segment the image. Apply Otsu's method for optimal thresholding

## Program
DEVELOPED BY : NAME - NANDIKA S 
REG NO - 212224230175

    import cv2
    import numpy as np
    import matplotlib.pyplot as plt
    image = cv2.imread('sample.jpg')  
    gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)  
    plt.subplot(2, 2, 1)
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB)) 
    plt.title("Original Image")
    plt.axis('off')
    _, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)
    adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)
    _, otsu_thresholded = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)
    
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

## Output

### Original Image
<img width="336" height="240" alt="image" src="https://github.com/user-attachments/assets/39d3483d-6b58-4cf3-9cb0-161da8de211c" />


### Global Thresholding
<img width="328" height="235" alt="image" src="https://github.com/user-attachments/assets/0e5905c5-f1d3-4f22-b18a-f5b5f01f2842" />


### Adaptive Thresholding
<img width="325" height="262" alt="image" src="https://github.com/user-attachments/assets/767187e1-3ec5-4204-b631-08447660a07a" />


### Optimum Global Thesholding using Otsu's Method
<img width="436" height="309" alt="image" src="https://github.com/user-attachments/assets/a2cfb7f1-fa0c-4f44-a0db-3d837ccf2ad1" />

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
