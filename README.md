# IMAGE-TRANSFORMATIONS


## Aim
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
```
1.Translation moves the image along the x or y-axis.
2.Scaling resizes the image by scaling factors.
3.Shearing distorts the image along one axis.
4.Reflection flips the image horizontally or vertically.
5.Rotation rotates the image by a given angle.
```
### Step4:
Display the transformed images using Matplotlib for visualization. Convert the BGR image to RGB format to ensure proper color representation.


### Step5:
Save or display the final transformed images for analysis and use plt.show() to display them inline in Jupyter or compatible environments.


## Program:
```python
Developed By: HARSHITHA V
Register Number: 212223230074
```
```
#import the libraries
import cv2
import numpy as np
import matplotlib.pyplot as plt

#Load the image and check if it's loaded correctly
input_img = cv2.imread(r"C:\Users\admin\Downloads\digitalimage\baby-moana.jpg")
if input_img is None:
    print("Error: Image not found.")
else:
    input_img = cv2.cvtColor(input_img, cv2.COLOR_BGR2RGB)

    # Display the image
    plt.figure(figsize=(8, 8))  # Optional: adjust size for better clarity
    plt.axis('off')
    plt.imshow(input_img)
    plt.title("Original Image")
    plt.tight_layout()  # Optional: makes sure layout is tight
    plt.show()

```
## i)Image Translation
```
#Get image dimensions
rows, cols, dim = input_img.shape

#Define translation matrix
translation_x = 50  # Move 50 pixels to the right
translation_y = 50  # Move 50 pixels down
M = np.float32([[1, 0, translation_x], [0, 1, translation_y]])

#Perform the translation
translated_img = cv2.warpAffine(input_img, M, (cols, rows))

#Display the translated image
plt.axis('off')
plt.imshow(translated_img)
plt.title("Translated Image")
plt.show()

```
## ii) Image Scaling
```
#Perform scaling with different scaling factors for x and y axes
fx, fy = 1.5, 2.0  # Scaling factors
scaled_img = cv2.resize(input_img, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)

#Show the scaled image
plt.axis('off')
plt.imshow(scaled_img)
plt.title("Scaled Image")
plt.show()

```
## iii)Image shearing
```
#Shearing in X-axis
shear_factor_x = 0.5  # Shear factor for X-axis
M_x = np.float32([[1, shear_factor_x, 0], [0, 1, 0]])

#Apply shearing
sheared_img_xaxis = cv2.warpAffine(input_img, M_x, (int(cols + shear_factor_x * rows), rows))

#Display the sheared image
plt.axis('off')
plt.title("Sheared X-axis")
plt.imshow(sheared_img_xaxis)

```
## iv)Image Reflection
```
#Flip image along the X-axis (vertical reflection)
reflected_img_xaxis = cv2.flip(input_img, 0)

#Display the reflected image
plt.axis("off")
plt.title("Reflected (X-axis)")
plt.imshow(reflected_img_xaxis)

```
## v)Image Rotation
```
#Get image dimensions
rows, cols = input_img.shape[:2]

#Define rotation center, angle, and scale
center = (cols // 2, rows // 2)
angle = 45  # Rotation angle in degrees
scale = 1.0  # Scale factor (1.0 means no scaling)

#Get the rotation matrix
M = cv2.getRotationMatrix2D(center, angle, scale)

#Apply the rotation
rotated_img = cv2.warpAffine(input_img, M, (cols, rows))

#Display the rotated image
plt.axis('off')
plt.title("Rotated Image (45°)")
plt.imshow(rotated_img)
plt.show()

```
## )Image Cropping
```
#Define the cropping coordinates: top-left corner (x, y) and width (w), height (h)
x, y, w, h = 400, 100, 1000, 500

#Crop the image by slicing the array
cropped_image = input_img[y:y+h, x:x+w]

#Display the cropped image (convert to RGB for correct color representation)
plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB))
plt.title("Cropped Image")
plt.axis('off')
plt.show()

```

## Output:
### Original Image

![image](https://github.com/user-attachments/assets/b9968e61-f6c8-4540-97b8-be93273dbe35)

### i)Image Translation

![image](https://github.com/user-attachments/assets/8355d1b3-07ce-46fe-8138-095ca280826c)

### ii) Image Scaling

![image](https://github.com/user-attachments/assets/c9ade080-f302-4741-8e0d-4a6266cb5050)

### iii)Image shearing

![image](https://github.com/user-attachments/assets/89145f41-9654-4785-8dbd-494d2e1923e8)

### iv)Image Reflection

![image](https://github.com/user-attachments/assets/6e1a5601-ddc1-4a79-a561-7c55bc9ca746)

### v)Image Rotation

![image](https://github.com/user-attachments/assets/b63525b4-4505-4eed-9186-58598832ee9d)

### vi)Image Cropping

![image](https://github.com/user-attachments/assets/01c9fc82-ba28-4c75-8e62-d3244a5d8ae2)




## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
