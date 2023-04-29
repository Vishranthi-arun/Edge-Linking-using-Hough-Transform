# Edge-Linking-using-Hough-Transform
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step 1:
Import all the necessary modules for the program.

### Step 2:
Load a image using imread() from cv2 module.

### Step 3:
Convert the image to grayscale.

### Step 4:
Using Canny operator from cv2,detect the edges of the image

### Step 5:
Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.

### Step 6:
Display the image and end the program.


## Program:


# Read image and convert it to grayscale image

import cv2
import matplotlib.pyplot as plt
import numpy as np

image = cv2.imread("exp8.jpg",0)
img = cv2.GaussianBlur(image,(3,3),0)

plt.axis('off')
plt.imshow(img)
plt.show()

# Find the edges in the image using canny detector and display

edge = cv2.Canny(img,60,90)
plt.imshow(edge,cmap='gray')
plt.title('Edge Image')
plt.xticks([])
plt.yticks([])
plt.show()



# Detect points that form a line using HoughLinesP

lines=cv2.HoughLinesP(edge,1,np.pi/180, threshold=80, minLineLength=50,maxLineGap=250)



# Draw lines on the image

for line in lines:
    x1,y1,x2,y2 = line[0]
    cv2.line(edge,(x1,y1),(x2,y2),(255,0,255),3)



# Display the result

plt.imshow(edge)
plt.axis('off')
plt.show()

## Output

### Input image and grayscale image
![image](https://user-images.githubusercontent.com/93992063/232981911-1d707477-9a7c-40dd-8300-d5e9972ae1f8.png)


### Canny Edge detector output
![image](https://user-images.githubusercontent.com/93992063/232982014-b2db0fdf-6429-4ce9-b156-dfa7bb046f0d.png)



### Display the result of Hough transform

![image](https://user-images.githubusercontent.com/93992063/232982802-4ed72a9d-8317-49f8-9b79-7f373cad0eb4.png)



## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform.
