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

## Program

```
Developed by : SUDHIR KUMAR. R
Register number : 212223230221
```

#### Input image and grayscale image

```python
import numpy as np
import cv2
import matplotlib.pyplot as plt
gray_img = cv2.imread(r"C:\Users\admin\dig-img-process\gray-fie.jpeg", cv2.IMREAD_GRAYSCALE)
img_c = cv2.imread(r"C:\Users\admin\dig-img-process\fie.jpg", cv2.IMREAD_COLOR)
img_c = cv2.cvtColor(img_c, cv2.COLOR_BGR2RGB)
gray_rgb = cv2.cvtColor(gray_img, cv2.COLOR_GRAY2RGB)
gray = cv2.GaussianBlur(gray_img, (3, 3), 0)
plt.figure(figsize=(13, 13))
plt.subplot(1, 2, 1)
plt.imshow(img_c)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1, 2, 2)
plt.imshow(gray, cmap='gray')
plt.title("Gray Image")
plt.axis("off")
plt.show()
```

### Canny Edge detector output

```python
import numpy as np
import cv2
import matplotlib.pyplot as plt

gray_img = cv2.imread(r"C:\Users\admin\dig-img-process\gray-fie.jpeg", cv2.IMREAD_GRAYSCALE)
img_c = cv2.imread(r"C:\Users\admin\dig-img-process\fie.jpg", cv2.IMREAD_COLOR)
img_c = cv2.cvtColor(img_c, cv2.COLOR_BGR2RGB)
gray_rgb = cv2.cvtColor(gray_img, cv2.COLOR_GRAY2RGB)

canny = cv2.Canny(gray_img, 120, 150)
plt.imshow(canny, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()
```

### Display the result of Hough transform

```python
import numpy as np
import cv2
import matplotlib.pyplot as plt

gray_img = cv2.imread(r"C:\Users\admin\dig-img-process\gray-fie.jpeg", cv2.IMREAD_GRAYSCALE)
img_c = cv2.imread(r"C:\Users\admin\dig-img-process\fie.jpg", cv2.IMREAD_COLOR)
img_c = cv2.cvtColor(img_c, cv2.COLOR_BGR2RGB)
canny = cv2.Canny(gray_img, 120, 150)
lines = cv2.HoughLinesP(canny, 1, np.pi/180, threshold=80, minLineLength=50, maxLineGap=250)
for line in lines:
    x1, y1, x2, y2 = line[0]
    cv2.line(img_c, (x1, y1), (x2, y2), (255, 0, 0), 3)
plt.imshow(img_c)
plt.title("Result Image with Hough Transform")
plt.axis("off")
plt.show()
```
## Output

### Input image and grayscale image

![Screenshot 2024-10-03 090218](https://github.com/user-attachments/assets/7a4d50f0-5bfb-4956-9456-22f7ee1e0af8)

### Canny Edge detector output

![Screenshot 2024-10-03 090355](https://github.com/user-attachments/assets/e5cef289-41af-4d67-9464-9f0c69537762)

### Display the result of Hough transform

![Screenshot 2024-10-03 090520](https://github.com/user-attachments/assets/0cea08b3-eeaf-4a90-8968-a2582fbb1569)

## Result :
Thus, the program to detect the lines using Hough Transform implemented successfully.
