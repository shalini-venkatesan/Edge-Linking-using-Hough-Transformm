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
```py
DEVELOPED BY: SHALINI V
REGISTER NO: 212222240096
```

### Read image and convert it to grayscale image:
```py
import numpy as np
import cv2
import matplotlib.pyplot as plt
img=cv2.imread("TM.jpg",0)
img_c=cv2.imread("TM.jpg",1)
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

### Find the edges in the image using canny detector and display:
```py
canny=cv2.Canny(gray,70,90)
plt.imshow(canny)
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()
```

### Detect points that form a line using HoughLinesP:
```py
lines=cv2.HoughLinesP(canny,1,np.pi/180,threshold=90,minLineLength=50,maxLineGap=90)
```

### Draw lines on the image:
```py
for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(img_c,(x1,y1),(x2,y2),(0,0,255),3)
```

### Display the result:
```py
plt.imshow(img_c)
plt.title("Result Image")
plt.axis("off")
plt.show()
```


## Output:

### Input image and grayscale image
![image](https://github.com/shalini-venkatesan/Edge-Linking-using-Hough-Transformm/assets/118720291/358daa3a-ee7c-4695-8f47-fc692c072492)

### Canny Edge detector output
![image](https://github.com/shalini-venkatesan/Edge-Linking-using-Hough-Transformm/assets/118720291/ffb684ef-0c2e-487d-ac8d-c20e7cfdbb0c)

### Display the result of Hough transform
![image](https://github.com/shalini-venkatesan/Edge-Linking-using-Hough-Transformm/assets/118720291/9a343afa-c421-4fe8-ab60-2ee155ab135e)

## Result:
Thus, the program is written with python and OpenCV to detect lines using Hough transform.
