# EXP:07 Edge-Linking-using-Hough-Transformm
# NAME: RAMYA.P
# REF NO: 212223240137

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

## program:
```PYTHON
# NAME: RAMYA.P
# REF NO: 212223240137

import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('/content/ramya photo.jpg') 
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
plt.title("Input Image")
plt.axis('off')
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
for line in lines:
    x1, y1, x2, y2 = line[0]
cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Result of Hough Transform")
plt.axis('off')
```
## Output

### Input image and grayscale image
<img width="250" height="321" alt="image" src="https://github.com/user-attachments/assets/5ebceb9a-8b07-417d-b26e-a3ab193d7b93" />


### Canny Edge detector output

<img width="251" height="326" alt="image" src="https://github.com/user-attachments/assets/7a9dd535-00e6-4b75-87f5-ebdb9640065c" />
<img width="251" height="332" alt="image" src="https://github.com/user-attachments/assets/51b1327a-c148-46e1-a9f9-ff3bafd8174d" />


### Display the result of Hough transform

<img width="250" height="327" alt="image" src="https://github.com/user-attachments/assets/01aa92c0-dbfa-4e96-8e0a-48deefb7a9c8" />

### Result 
Thus,The Python program to detect the lines using Hough Transform run successfully.

