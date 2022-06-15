# Thresholding of Images
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm
Step 1: Load the necessary packages.

Step 2: Read the Image and convert to grayscale.

Step 3: Use Global thresholding to segment the image.

Step 4: Use Adaptive thresholding to segment the image.

Step 5: Use Otsu's method to segment the image.

Step 6: Display the results.

## Program

```

import cv2
import matplotlib.pyplot as plt
image = cv2.imread("mountain.jpg")


# Read the Image and convert to grayscale

grayImage = cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)


# Use Global thresholding to segment the image


ret,thresh = cv2.threshold(grayImage,100,200,cv2.THRESH_BINARY)
ret1,thresh1 = cv2.threshold(grayImage,100,200,cv2.THRESH_BINARY_INV)
ret2, thresh2 = cv2.threshold(grayImage,100,200,cv2.THRESH_TRUNC)
ret3, thresh3 = cv2.threshold(grayImage,100,200,cv2.THRESH_TOZERO)
ret4, thresh4 = cv2.threshold(grayImage,100,200,cv2.THRESH_TOZERO_INV)





# Use Adaptive thresholding to segment the image

th1 = cv2.adaptiveThreshold(grayImage,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
th2 = cv2.adaptiveThreshold(grayImage,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
titles = ["Original Image","Adaptive Mean Thresholding","Adaptive Gaussian Thresholding"]
imgs = [grayImage,th1,th2]




# Use Otsu's method to segment the image 
ret5,th3 = cv2.threshold(grayImage,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)



# Display the results

cv2.imshow("Original Image",image)
cv2.imshow("Gray Image",grayImage)
cv2.imshow("THRESH_BINARY",thresh)
cv2.imshow("THRESH_BINARY_INV",thresh1)
cv2.imshow("THRESH_TRUNC",thresh2)
cv2.imshow("THRESH_TOZERO",thresh3)
cv2.imshow("THRESH_TOZERO_INV",thresh4)

for i in range(3):
    plt.subplot(3,1,i+1)
    plt.imshow(imgs[i],'gray')
    plt.title(titles[i])
    plt.xticks([]),plt.yticks([])
plt.show()


cv2.imshow("Otsu method",th3)




```
## Output

### Original Image
![s1](https://user-images.githubusercontent.com/93427186/173892275-47975e65-2d60-4091-a0f6-2c8643e8811f.png)
![s2](https://user-images.githubusercontent.com/93427186/173892295-e5fc6f9d-b873-4095-89cd-5a59c00bf19f.png)


### Global Thresholding

![s3](https://user-images.githubusercontent.com/93427186/173892329-797613a3-92bb-4d10-89f0-30f7bf343d23.png)
![s4](https://user-images.githubusercontent.com/93427186/173892376-67d6ba70-bf14-4b11-a53b-f476a4159ed8.png)
![s6](https://user-images.githubusercontent.com/93427186/173892413-b1a3b874-2d03-41fe-b786-0b3e31a12b91.png)


### Adaptive Thresholding
![s7](https://user-images.githubusercontent.com/93427186/173892452-aa7ef9ce-f8b9-428e-b8eb-ac57552cbc4e.png)
![s8](https://user-images.githubusercontent.com/93427186/173892461-f8ecd99c-e831-4daf-a7dc-a9324e62c8fe.png)


### Optimum Global Thesholding using Otsu's Method

![s9](https://user-images.githubusercontent.com/93427186/173892487-7d1dc2db-d709-4ceb-804e-ad9733e767a3.png)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

