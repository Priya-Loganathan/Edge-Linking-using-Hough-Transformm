# Edge-Linking-using-Hough-Transformm
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import all the necessary modules for the program.
### Step2:

Load a image using imread() from cv2 module.
### Step3:

Convert the image to grayscale.
### Step4:

Using Canny operator from cv2,detect the edges of the image.
### Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

## Program:
```
DEVELOPED BY: DELLI PRIYA L
REG NO: 212222230029
```
### Read image and convert it to grayscale image
```
import numpy as np
import cv2
import matplotlib.pyplot as plt
img=cv2.imread("car.png",0)
img_c=cv2.imread("car.png",1)
img_c=cv2.cvtColor(img_c,cv2.COLOR_BGR2RGB)
gray=cv2.cvtColor(img,cv2.COLOR_GRAY2RGB)
gray = cv2.GaussianBlur(gray,(3,3),0)
plt.figure(figsize=(13,13))
plt.subplot(1,2,1)
plt.imshow(img_c)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gray)
plt.title("Gray Image")
plt.axis("off")
plt.show()
```
![325715627-c0375db5-220b-495c-9cb7-ca3f7fd9fb01](https://github.com/Priya-Loganathan/Edge-Linking-using-Hough-Transformm/assets/121166075/9c5c7059-2484-4e3d-bb62-4ddf3572d978)

### Find the edges in the image using canny detector and display
```
canny=cv2.Canny(gray,120,150)
plt.imshow(canny)
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()
```
![325715904-89dbc795-cfc0-4afe-a6d3-89d851b7c587](https://github.com/Priya-Loganathan/Edge-Linking-using-Hough-Transformm/assets/121166075/b6580bf5-c784-4a16-aad6-68993a4f69bb)

### Detect points that form a line using HoughLinesP
```
lines=cv2.HoughLinesP(canny,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=250)
```
### Draw lines on the image
```
for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(img_c,(x1,y1),(x2,y2),(255,0,0),3)
```

### Display the result of Hough transform
```
plt.imshow(img_c)
plt.title("Result Image")
plt.axis("off")
plt.show()
```
![325716272-1605ac05-3172-4acd-8ed9-f7ebe0042b7d](https://github.com/Priya-Loganathan/Edge-Linking-using-Hough-Transformm/assets/121166075/b5965dc5-ce57-4629-8af9-e50fd0c7bfd9)

## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform.
