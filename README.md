# Thresholding
## AIM:
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## SOFTWARE REQUIRED:
1. Anaconda - Python 3.7
2. OpenCV

## ALGORITHM:

### Step 1:
Load the necessary packages.

### Step 2:
Read the Image and convert to grayscale.

### Step 3:
Use Global thresholding to segment the image.

### Step 4:
Use Adaptive thresholding to segment the image.

### Step 5:
Use Otsu's method to segment the image.

### Step 6:
Display the results.

## PROGRAM:
```python
# Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale
image=cv2.imread("img.jpg",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("img.jpg",0)

# Use Global thresholding to segment the image
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Adaptive thresholding to segment the image
thresh_img7=cv2.adaptive Threshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptive Threshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

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
## OUTPUT:

### Original Image and Grayscale Image

![1](https://user-images.githubusercontent.com/75234991/169071832-5e558ef9-1f55-463a-9164-d8afc455d7e5.png)

### Global Thresholding

![2](https://user-images.githubusercontent.com/75234991/169071852-98d7c675-08da-491b-974d-c21c6e8e12df.png)

![3](https://user-images.githubusercontent.com/75234991/169071943-0836ded7-a61d-4db1-879e-d2641830a018.png)

![4](https://user-images.githubusercontent.com/75234991/169071950-715afa7b-2dfa-47dc-a239-0c66b73564b3.png)

![5](https://user-images.githubusercontent.com/75234991/169071962-c9353819-eb1b-4491-8e13-13f92f9142d4.png)

![6](https://user-images.githubusercontent.com/75234991/169071979-3dfa13f7-66db-494d-99a7-e03e681b7880.png)

### Adaptive Thresholding

![7](https://user-images.githubusercontent.com/75234991/169072009-d906532c-a3e9-407b-8270-7c8ac992104e.png)

![8](https://user-images.githubusercontent.com/75234991/169072024-5868900b-8453-46be-84a0-81e864e5520d.png)

### Optimum Global Thesholding using Otsu's Method

![9](https://user-images.githubusercontent.com/75234991/169072049-0de0b66f-6720-42a4-93fd-32e2169e6211.png)

## RESULT:
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
