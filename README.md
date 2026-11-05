## Record-Image-Transformations
## Geometric Transformations Using OpenCV:

## Aim:

To write a Python program using OpenCV to perform various geometric transformations on an image.

## The program performs the following operations:

* Image Translation
* Image Scaling (Resizing)
* Image Shearing
* Image Reflection (Flipping)
* Image Rotation

## Software Used:

* Anaconda – Python 3.7
* Jupyter Notebook / VS Code
* OpenCV (cv2)
* NumPy
* Matplotlib

## Algorithm:

## Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

## Step 2:
Read the input image in color mode.

## Step 3: Image Translation

* Create a translation matrix to shift the image
* Move the image 50 pixels to the right and 80 pixels down
* Apply transformation using cv2.warpAffine()
* Display original and translated images

## Step 4: Image Scaling

* Resize the image to 0.5× (downscale)
* Resize the image to 2× (upscale)
* Use cv2.resize()
* Display original, downscaled, and upscaled images

## Step 5: Image Shearing

* Create transformation matrices for:
  * Horizontal shearing
  * Vertical shearing
* Apply transformations using cv2.warpAffine()
* Display original and sheared images

## Step 6: Image Reflection

* Perform flipping using cv2.flip():
  * Horizontal reflection
  * Vertical reflection
  * Both axes
* Display all reflected images

## Step 7: Image Rotation

* Create rotation matrices for:
  * 45° rotation
  * 90° rotation
* Use cv2.getRotationMatrix2D() and cv2.warpAffine()
* Display original and rotated images

## Program:

## Developed By: LOGESHWARAN R

## Register No: 212225040205

### ORIGINAL IMAGE:

```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

```
image = cv2.imread('sai1.jpeg')
```

```
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB)) 
plt.title("Original Image")  
plt.axis('off') 
```

## TRANSLATED IMAGE:

```
tx, ty = 100, 50  
M_translation = np.float32([[1, 0, tx], [0, 1, ty]])  
translated_image = cv2.warpAffine(image, M_translation, (image.shape[1], image.shape[0]))  
```

```
plt.imshow(cv2.cvtColor(translated_image, cv2.COLOR_BGR2RGB)) 
plt.title("Translated Image")  
plt.axis('off')
```

## SCALED IMAGE: 

```
fx, fy = 5.0, 2.0  
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)
```

```
plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB))  
plt.title("Scaled Image")  
plt.axis('off')
```

## SHEARED IMAGE:

```
shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))
```

```
plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB)) 
plt.title("Sheared Image") 
plt.axis('off')
```

## REFLECTED IMAGE:

```
reflected_image = cv2.flip(image, 2)
```

```
plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB))  
plt.title("Reflected Image")  
plt.axis('off')
```

## ROTATED IMAGE:

```
(height, width) = image.shape[:2] 
angle = 45 
center = (width // 2, height // 2) 
M_rotation = cv2.getRotationMatrix2D(center, angle, 1)
rotated_image = cv2.warpAffine(image, M_rotation, (width, height)) 
```

```
plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB))  
plt.title("Rotated Image") 
plt.axis('off')
```

## CROPPED IMAGE:

```
x, y, w, h = 100, 100, 200, 150 
cropped_image = image[y:y+h, x:x+w]
```

```
plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB))  
plt.title("Cropped Image")
plt.axis('off')
```

## OUTPUT:

## Original Image:

<img width="237" height="410" alt="image" src="https://github.com/user-attachments/assets/b6e3861e-394c-4e9b-b9ab-39aa80bf65d5" />


## Image Translation:

<img width="235" height="420" alt="image" src="https://github.com/user-attachments/assets/62d2601f-4a24-4039-ac90-e860c30634ac" />

## Image Scaling:

<img width="492" height="412" alt="image" src="https://github.com/user-attachments/assets/62a2943b-f22e-4c73-8dfe-6b821b7657df" />

## Image Shearing:

<img width="253" height="420" alt="image" src="https://github.com/user-attachments/assets/493cb9fd-7400-4776-a2f8-af70bdc4651d" />

## Image Reflection:

<img width="216" height="406" alt="image" src="https://github.com/user-attachments/assets/6cde39d4-bab8-4ef8-aab4-416f797a5076" />

## Image Rotation:

<img width="220" height="407" alt="image" src="https://github.com/user-attachments/assets/05d5e585-9f7c-4a85-9a85-0d9d3dc39725" />

## Image Cropping:

<img width="452" height="407" alt="image" src="https://github.com/user-attachments/assets/e3847edd-ebb6-42c6-bce9-3282d568bb85" />

## RESULT:

Thus, various geometric transformations such as translation, scaling, shearing, reflection, and rotation are successfully performed using OpenCV. These transformations demonstrate how images can be spatially manipulated for different computer vision applications.
