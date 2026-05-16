# Edge-Linking-using-Hough-Transformm
## Experiment No: 7
## Name:
Dharanya N
## Register Number:
212223230044

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

Developed by : DHARANYA N

Register no : 212223230044

### Read image and convert it to grayscale image
```
import numpy as np
import cv2
import matplotlib.pyplot as plt
img=cv2.imread("Qn_7_.jpg",0)
img_c=cv2.imread("Qn_7_.jpg",1)
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
### Find the edges in the image using canny detector and display
```
canny=cv2.Canny(gray,70,90)
plt.imshow(canny)
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()
```
### Display the result of Hough transform
```
lines=cv2.HoughLinesP(canny,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=250)
for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(img_c,(x1,y1),(x2,y2),(255,0,0),3)
    plt.imshow(img_c)
plt.title("Result Image")
plt.axis("off")
plt.show()
```
## Output

### Input image and grayscale image
<img width="1027" height="363" alt="download" src="https://github.com/user-attachments/assets/18f174b7-f642-4e9e-b657-78b3404ea2f7" />

### Canny Edge detector output
<img width="515" height="390" alt="download" src="https://github.com/user-attachments/assets/9823b491-3699-44ea-a4ba-b4e0591b5c98" />

### Display the result of Hough transform
<img width="515" height="390" alt="download" src="https://github.com/user-attachments/assets/db8d15f9-4cb3-404e-a4b8-2fecf44a15d6" />



## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform.
