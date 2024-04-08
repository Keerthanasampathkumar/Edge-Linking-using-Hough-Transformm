# EX-07 EDGE LINKING HOUGH TRANSFORM
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read image and convert it to grayscale image.

### Step2:
Find the edges in the image using canny detector and display.

### Step3:
Detect points that form a line using HoughLinesP.

### Step4:
Draw lines on the image.

### Step5:
Display the result.

## Program:
```
DEVELOPED BY: KEERTHANA S
REGISTER NUMBER: 212222230066
```

### Read image and convert it to grayscale image
```p
import numpy as np
import cv2
import matplotlib.pyplot as plt
img=cv2.imread("jin.jpg",0)
img_c=cv2.imread("jin.jpg",1)
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
```p
canny=cv2.Canny(gray,120,150)
plt.imshow(canny)
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()
```
### Detect points that form a line using HoughLinesP
```p
lines=cv2.HoughLinesP(canny,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=250)
```
### Draw lines on the image
```p
for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(img_c,(x1,y1),(x2,y2),(255,0,0),3)
```
### Display the result
```p
plt.imshow(img_c)
plt.title("Result Image")
plt.axis("off")
plt.show()
```
## Output

### Input image and grayscale image
![Screenshot 2024-04-03 082127](https://github.com/abinayasangeetha/Edge-Linking-using-Hough-Transformm/assets/119393675/28902fd6-5421-4aad-af48-e2bb957c0018)


<br>

### Canny Edge detector output
![Screenshot 2024-04-03 082138](https://github.com/abinayasangeetha/Edge-Linking-using-Hough-Transformm/assets/119393675/d4cdbec3-81b6-4d8f-a351-876adc96d521)


<br>

### Display the result of Hough transform
![Screenshot 2024-04-03 082206](https://github.com/abinayasangeetha/Edge-Linking-using-Hough-Transformm/assets/119393675/8075a6ce-6878-4c91-9733-e3898ed8e496)


<br>

## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform.
