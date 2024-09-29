# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
<br>
Load the necessary packages.

### Step2:
<br>
Read the Image and convert to grayscale.

### Step3:
<br>
Use Global thresholding to segment the image.

### Step4:
<br>
Use Adaptive thresholding to segment the image.

### Step5:
<br>
Use Otsu's method to segment the image and display the results.

### Program
```
Developed By : PRADEEP S
Register Number : 212222100034
```

### Load the necessary packages:
```PY
import numpy as np
import matplotlib.pyplot as plt
import cv2
```

# Read the Image and convert to grayscale
```PY
image = cv2.imread('lion.jpg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('lion.jpg',0)
```
# Use Global thresholding to segment the image
```PY
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
# Use Adaptive thresholding to segment the image
```PY
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
# Use Otsu's method to segment the image 
```PY
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
# Display the results
```PY
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
### Output

### Original Image

![lion1](https://github.com/user-attachments/assets/c1139445-4768-420b-aec4-95a47e31d0e9)


### Global Thresholding

![lion2](https://github.com/user-attachments/assets/d059ed24-d28a-4818-af46-047d7987ef34)

![lion3](https://github.com/user-attachments/assets/d1851dd8-436d-4929-840d-6246dd32566d)

![lion4](https://github.com/user-attachments/assets/5213c2ea-12be-47f8-a59c-68df8a03ad57)

![lion5](https://github.com/user-attachments/assets/a14fc216-6d7d-4f64-8a96-6834566a61d7)

![lion6](https://github.com/user-attachments/assets/cda4e2e9-0062-4a69-b1b9-935d4c25bb44)


### Adaptive Thresholding

![lion8](https://github.com/user-attachments/assets/ef414f9d-d4f0-44c1-ae51-d93b4afcb101)

![lion9](https://github.com/user-attachments/assets/2db84018-10c3-4236-8fa2-93408c9d75d7)


### Optimum Global Thesholding using Otsu's Method

![lion7](https://github.com/user-attachments/assets/e2c6d538-5199-4b87-8e3e-705f65ad49e3)



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
