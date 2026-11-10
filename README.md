# EXP 06 - Record-EDGE DETECTION
## NAME: ALAGESHWARI V
## REG NO: 212224240010

### AIM:

To implement edge detection techniques such as Sobel, Laplacian, and Canny using OpenCV and Python to identify the edges in an image.

### PROCEDURE:

1.Import the required libraries such as OpenCV, NumPy, and Matplotlib.

2.Read the input image using cv2.imread().

3.Convert the original image into a grayscale image using cv2.cvtColor().

4.Apply the Sobel operator in the X and Y directions to detect edges.

5.Combine both Sobel outputs using cv2.magnitude().

6.Apply the Laplacian operator to detect edges in the image.

7.Apply the Canny edge detection technique using cv2.Canny().

8.Display the original image and the detected edges using Matplotlib.

### CODE:
```python

import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('photo.png')  # Replace with your image path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
# Original Image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')
sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  # Sobel in x direction
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  # Sobel in y direction
sobel_combined = cv2.magnitude(sobel_x, sobel_y)  # Combine both directions
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')
laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)
plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')
canny_edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')
```

### OUTPUT:

<img width="688" height="530" alt="image" src="https://github.com/user-attachments/assets/bf8dad2c-30bd-4dc7-93f8-c28e92de267c" />

<img width="698" height="528" alt="image" src="https://github.com/user-attachments/assets/3a82f5cf-69d8-4149-becd-95e66bc7fb2f" />

<img width="693" height="527" alt="image" src="https://github.com/user-attachments/assets/cddadd7d-d4a1-459a-931c-9da6e09e4098" />

<img width="693" height="532" alt="image" src="https://github.com/user-attachments/assets/bf39d43b-0a76-4177-9e7f-6fc6d156c40f" />

### RESULT:

Thus, the edge detection techniques such as Sobel, Laplacian, and Canny were successfully implemented using OpenCV and Python. The edges of the input image were detected and displayed successfully.
