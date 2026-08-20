## Exp-7-Record-HOUGH TRANSFORM

##  Aim

To implement a basic lane detection pipeline using OpenCV by completing missing code segments at specified locations.

## Learning Objective

* Understand each stage of image processing
* Learn how to build a complete computer vision pipeline
* Practice writing code in guided sections

##  Software Used

* Anaconda – Python 3.7
* Jupyter Notebook / VS Code
* OpenCV (cv2)
* NumPy
* Matplotlib

##  Algorithm & Explanation

##  Developed By

* **Name:** Niranjani.C
* **Register No:** 212223220069


###  Step 1: Import Libraries

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

---

###  Step 2: Read the Image

```python
# Step 2: Load the image using imread() from cv2 module
image = cv2.imread('road.png')  # Replace 'image.jpg' with your image path
```

###  Step 3: Convert to Grayscale

```python
# Step 3: Convert the image to grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

```

###  Step 4: Display Images

```python
# Input image and grayscale image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
plt.title("Input Image")
plt.axis('off')
```

###  Step 5: Thresholding

```python
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
```

###  Step 6: Region of Interest (ROI)

```python
# Step 4: Using Canny operator from cv2, detect the edges of the image
edges = cv2.Canny(gray_image, 50, 150)  # Canny edge detection with threshold values 50 and 150

```

### Step 7: Edge Detection (Canny)

```python
# Canny Edge Detector output
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
```

###  Step 8: Gaussian Blur

```python
# Step 5: Using the HoughLinesP(), detect line coordinates for every point in the image
# The parameters of HoughLinesP are: image, resolution, threshold, minLineLength, maxLineGap
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)

```


###  Step 9: Hough Transform

```python
# Step 6: Using a for loop, draw the lines on the original image using the detected coordinates
# The lines variable contains the endpoints of the detected lines
for line in lines:
    x1, y1, x2, y2 = line[0]  # Unpacking the line coordinates
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)  # Draw green lines with thickness of 2

```

### Step 10: Lane Detection Logic

```python
# Display the result of Hough Transform (Image with lines)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Image with lines drawn
plt.title("Result of Hough Transform")
plt.axis('off')
```

##  Expected Output

<img width="1919" height="717" alt="image" src="https://github.com/user-attachments/assets/5b84243e-036d-42fa-b6ed-130da46e6336" />

<img width="1919" height="672" alt="image" src="https://github.com/user-attachments/assets/a3c7766f-a9ee-4679-9db3-59263b5ff4b6" />

<img width="1911" height="649" alt="image" src="https://github.com/user-attachments/assets/5e53ea5f-5c00-487f-ab1c-16ae87cd6362" />

<img width="1919" height="800" alt="image" src="https://github.com/user-attachments/assets/86e7b76c-11ef-430e-bfd8-ea4324ba7072" />

## Result

Thus, the lane detection pipeline is successfully implemented by completing the missing code sections. The system detects and highlights lane lines effectively.




