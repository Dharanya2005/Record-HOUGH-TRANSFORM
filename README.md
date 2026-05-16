# Record-HOUGH-TRANSFORM
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
# Program:
### **Step 1: Read and Display Image**
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('Qn_7_.jpg') 
```

### **Step 2: Convert the image to grayscale**
```python
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
```

### **Step 3: Input image and grayscale image**
```python
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
plt.title("Input Image")
plt.axis('off')
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
```

### **Step 4: Using Canny operator from cv2, detect the edges of the image**
```python
edges = cv2.Canny(gray_image, 50, 150)
```

### **Step 5:Canny Edge Detector output**
```python
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
```

### **Step 6: Using the HoughLinesP(), Cfor every point in the image**
```python
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
```

### **Step 7:Draw the lines on the original image using the detected coordinates**
```python
for line in lines:
    x1, y1, x2, y2 = line[0]  # Unpacking the line coordinates
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)  # Draw green lines with thickness of 2
```

### **Step 8:Display the result of Hough Transform (Image with lines)**
```python
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Image with lines drawn
plt.title("Result of Hough Transform")
plt.axis('off')
```
## Output

### Input image and grayscale image
<img width="515" height="390" alt="download" src="https://github.com/user-attachments/assets/62ab516d-aa71-4ffc-969d-318402801811" />
<img width="515" height="390" alt="download" src="https://github.com/user-attachments/assets/715b361a-e847-49a4-8efa-aebba74ef2e1" />


### Canny Edge detector output
<img width="515" height="390" alt="download" src="https://github.com/user-attachments/assets/644c61ca-344d-483a-85e7-8e604be10270" />

### Display the result of Hough transform

<img width="515" height="390" alt="download" src="https://github.com/user-attachments/assets/3c6b91be-1619-4b5f-a706-4b66df082ad1" />

## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform.
