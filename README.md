# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages.

### Step2:
Read the Image and convert to grayscale.

### Step3:
Use Global thresholding to segment the image.

### Step4:
Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image and display the results.

## Program

```python

#Developed by : Renusri Naraharashetty
#Register No: 212223240139

# Load the necessary packages

import numpy as np
import matplotlib.pyplot as plt
import cv2

# Read the Image and convert to grayscale

image = cv2.imread('boy.jpg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('boy.jpg',0)

# Use Global thresholding to segment the image

ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Adaptive thresholding to segment the image

thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Use Otsu's method to segment the image 

ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Display the results

titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)",
        "Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)",
        "Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()


```
## Output

### Original Image
![image](https://github.com/user-attachments/assets/e16e5aa1-50c0-4773-9937-583feac508c9)


### Global Thresholding
![image](https://github.com/user-attachments/assets/3a451810-bc87-4941-8c41-7d85181639da)
![image](https://github.com/user-attachments/assets/5886f7e2-b860-47e7-ab7c-593e32952c3e)
![image](https://github.com/user-attachments/assets/b07a88b7-5ae8-4082-8c27-19340990600f)
![image](https://github.com/user-attachments/assets/03237cef-aa6f-4a35-a9bd-9a3283608c1b)
![image](https://github.com/user-attachments/assets/99540826-16cd-4860-b110-177e07415e1a)


### Adaptive Thresholding
![image](https://github.com/user-attachments/assets/5fba81c0-c01a-4f4c-9efd-35dc7fe93f99)
![image](https://github.com/user-attachments/assets/6e9fb2cb-5683-462a-ab38-a086cb1b8144)


### Optimum Global Thesholding using Otsu's Method
![image](https://github.com/user-attachments/assets/43026478-1e43-4805-8e2d-9aa2b50fb312)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
