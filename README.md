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
![image](https://user-images.githubusercontent.com/93427186/173877555-5b9407e1-944e-446f-8d5a-f419cd15045d.png)

### Global Thresholding
![image](https://user-images.githubusercontent.com/93427186/173877661-3d6ebeb3-f0da-4c87-93dc-dfbb85789cde.png)


### Adaptive Thresholding
![image](https://user-images.githubusercontent.com/93427186/173877703-ff565124-db72-4d33-804f-3c972478ea60.png)

### Optimum Global Thesholding using Otsu's Method
![image](https://user-images.githubusercontent.com/93427186/173877822-2a94e474-be50-4dc0-ab81-268e9479f0dd.png)

### Use Otsu's method to segment the image 
![image](https://user-images.githubusercontent.com/93427186/173877907-c9eb9a7e-2bf2-47bf-953c-6a28f052cbae.png)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

