# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step 1:
Load the necessary packages.
<br>
### Step 2:
Read the Image and convert to grayscale.
<br>
### Step 3:
Use Global thresholding to segment the image.
<br>
### Step 4:
Use Adaptive thresholding to segment the image.
<br>
### Step 5:
Use Otsu's method to segment the image.
<br>
### Step 6:
Display the results.
<br>
## Program

```python
# Load the necessary packages
import numpy as np
import matplotlib.pyplot as plt
import cv2

# Read the Image and convert to grayscale
image = cv2.imread("mashabear.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("mashabear.jpg",0)

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
![image](https://github.com/swethamohanraj/Thresholdingg/assets/94228215/2b2d7b9e-9838-4bc7-a092-65b0de379717)


### Global Thresholding
![image](https://github.com/swethamohanraj/Thresholdingg/assets/94228215/cad757fc-ee8a-4e93-94bf-711ca0dc8478)
![image](https://github.com/swethamohanraj/Thresholdingg/assets/94228215/8e3f6dc0-4c31-436a-a249-ab95a645cb6f)
![image](https://github.com/swethamohanraj/Thresholdingg/assets/94228215/dafafa87-8de3-4c70-890f-99b45848b511)
![image](https://github.com/swethamohanraj/Thresholdingg/assets/94228215/7edbcb5d-f79a-4886-9e1b-2cc33f61e0d5)
![image](https://github.com/swethamohanraj/Thresholdingg/assets/94228215/9fdfec94-8b33-4467-a3fd-0c38a3135ac8)


### Adaptive Thresholding
![image](https://github.com/swethamohanraj/Thresholdingg/assets/94228215/09d3ef8b-32d5-42c4-8df7-5b07214ed3af)
![image](https://github.com/swethamohanraj/Thresholdingg/assets/94228215/546ef20c-67ed-4e1e-9b08-69b4728c65c5)


### Optimum Global Thesholding using Otsu's Method
![Uploading image.png…]()


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
