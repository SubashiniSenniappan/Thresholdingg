![download](https://github.com/user-attachments/assets/f4b1a912-e156-4a6e-aac9-87f957cc05db)# EX 8 - THRESHOLDING
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
### Developed By :SUBASHINI S
### Register Number : 212222240106
```python
# Load the necessary packages
import numpy as np
import matplotlib.pyplot as plt
import cv2

# Read the Image and convert to grayscale
image = cv2.imread('alchemy of souls.jpg.jpg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('love.jpg',0)

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
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
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


![download](https://github.com/user-attachments/assets/e567af0f-7ee4-4217-a724-8c48e8be57e6)


### Global Thresholding

![download (1)](https://github.com/user-attachments/assets/4faf9f84-5084-40dd-91e2-31aa65841b6a)

![download (2)](https://github.com/user-attachments/assets/b5a9ec7a-475d-4c49-8950-eef91878f1ab)

![download (4)](https://github.com/user-attachments/assets/2d672ab0-20e1-4529-995a-717f72edced0)

![download (5)](https://github.com/user-attachments/assets/87c81a56-d406-42ef-955a-d81c069ebaec)

### Adaptive Thresholding

![download (8)](https://github.com/user-attachments/assets/deb24161-cfd8-4d8b-ba84-f3e2acf9b6a0)

![download (9)](https://github.com/user-attachments/assets/808b9a78-44a8-40c6-8610-7f05e4e98cfb)


### Optimum Global Thesholding using Otsu's Method


![download (7)](https://github.com/user-attachments/assets/71a7bea2-c624-4581-880f-7e0b4a51683a)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

