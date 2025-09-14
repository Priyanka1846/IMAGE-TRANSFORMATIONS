# IMAGE-TRANSFORMATIONS


## Aim:
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import necessary libraries such as OpenCV, NumPy, and Matplotlib for image processing and visualization.

### Step2:

Read the input image using cv2.imread() and store it in a variable for further processing.

### Step3:
Apply various transformations like translation, scaling, shearing, reflection, rotation, and cropping by defining corresponding functions:

1.Translation moves the image along the x or y-axis. 

2.Scaling resizes the image by scaling factors. 

3.Shearing distorts the image along one axis. 

4.Reflection flips the image horizontally or vertically. 

5.Rotation rotates the image by a given angle.

### Step4:
Display the transformed images using Matplotlib for visualization. Convert the BGR image to RGB format to ensure proper color representation.

### Step5:
Save or display the final transformed images for analysis and use plt.show() to display them inline in Jupyter or compatible environments.

## Program:
```python
Developed By: Priyanka K
Register Number: 212223230162

import cv2
import matplotlib.pyplot as plt
import numpy as np

# Load image
img = cv2.imread('nature.jpg')
print("Original Image Shape:", img.shape)

# Show Original Image
plt.imshow(cv2.cvtColor(img, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('on')
plt.show()

# ---------------- Image Translation ----------------
tx, ty = 200, 400
trans = np.float32([[1, 0, tx], [0, 1, ty]])
trans_img = cv2.warpAffine(img, trans, (1536, 1024))

plt.imshow(cv2.cvtColor(trans_img, cv2.COLOR_BGR2RGB))
plt.title('Translated Image')
plt.axis('on')
plt.show()

# ---------------- Image Scaling ----------------
fx, fy = 3.0, 1.0
scaled = cv2.resize(img, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)

plt.imshow(cv2.cvtColor(scaled, cv2.COLOR_BGR2RGB))
plt.title('Scaled Image')
plt.axis('on')
plt.show()

# ---------------- Image Shearing ----------------
shear_matrix = np.float32([[1, 0.3, 0], [0.3, 1, 0]])
shear_img = cv2.warpAffine(img, shear_matrix, (1536, 1024))

plt.imshow(cv2.cvtColor(shear_img, cv2.COLOR_BGR2RGB))
plt.title("Sheared Image")
plt.axis('on')
plt.show()

# ---------------- Image Reflection ----------------
reflected = cv2.flip(img, 1)  # Horizontal reflection

plt.figure(figsize=(10, 5))
plt.subplot(1, 2, 2)
plt.imshow(cv2.cvtColor(reflected, cv2.COLOR_BGR2RGB))
plt.title('Reflected Image')
plt.axis('off')
plt.tight_layout()
plt.show()

# ---------------- Image Rotation ----------------
(height, width) = img.shape[:2]
angle = 45
center = (width // 2, height // 2)
rot = cv2.getRotationMatrix2D(center, angle, 1)
rot_img = cv2.warpAffine(img, rot, (width, height))

plt.imshow(cv2.cvtColor(rot_img, cv2.COLOR_BGR2RGB))
plt.title("Rotated Image")
plt.axis('off')
plt.show()

# ---------------- Image Cropping ----------------
x, y, w, h = 50, 100, 300, 200
cropped = img[y:y+h, x:x+w]

plt.figure(figsize=(10, 5))
plt.subplot(1, 2, 2)
plt.imshow(cv2.cvtColor(cropped, cv2.COLOR_BGR2RGB))
print("Shape of cropped image:", cropped.shape)
plt.title("Cropped Image")
plt.axis('on')
plt.tight_layout()
plt.show()

```
## Output:
<img width="556" height="373" alt="image" src="https://github.com/user-attachments/assets/00167a54-3139-461c-95e6-af5c5b8ff447" />
<img width="561" height="394" alt="image" src="https://github.com/user-attachments/assets/17709b2c-9b1f-4b41-97a4-6c68d628bf99" />
<img width="552" height="167" alt="image" src="https://github.com/user-attachments/assets/65fcf73a-04e0-4393-845e-269ef5efab23" />
<img width="561" height="394" alt="image" src="https://github.com/user-attachments/assets/98c3a6be-c2e8-42f3-a4a8-366df593c6ab" />
<img width="497" height="338" alt="image" src="https://github.com/user-attachments/assets/d7d6f0d3-d779-4423-8cf6-b3e38ff37c23" />
<img width="515" height="349" alt="image" src="https://github.com/user-attachments/assets/24fe178e-479b-4329-88da-0861354d34af" />
<img width="515" height="370" alt="image" src="https://github.com/user-attachments/assets/bcb7f4ae-e315-4f4e-a857-ddb0bbcda7b6" />

## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
