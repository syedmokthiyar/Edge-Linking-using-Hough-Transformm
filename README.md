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

## Developed by: Syed Mokthiyar S M
## Reg no: 212222230156m 

## Image Processing:
```python
import numpy as np
import cv2
import matplotlib.pyplot as plt
img=cv2.imread("dog.jpeg",0)
img_c=cv2.imread("dog.jpeg",1)
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
## Canny Edge Detection:
```python
canny=cv2.Canny(gray,120,150)
plt.imshow(canny)
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()
```
## Hough Transform:
```python
lines=cv2.HoughLinesP(canny,1,np.pi/180,threshold=60,minLineLength=40,maxLineGap=200)
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

![Screenshot 2024-04-03 082958](https://github.com/Gokul0117/Edge-Linking-using-Hough-Transformm/assets/121165938/7031584a-5d38-4f79-b015-285a15bd3f28)


### Canny Edge detector output

![Screenshot 2024-04-03 083013](https://github.com/Gokul0117/Edge-Linking-using-Hough-Transformm/assets/121165938/3c4a0e67-d2a4-495b-b3c6-37d232c6ac27)


### Display the result of Hough transform

![Screenshot 2024-04-03 083020](https://github.com/Gokul0117/Edge-Linking-using-Hough-Transformm/assets/121165938/756c4d35-f062-4446-8a29-afaf4778e78a)

## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform.
