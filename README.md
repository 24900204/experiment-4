# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step 1: 
Import the required libraries such as OpenCV (cv2), NumPy, and Matplotlib.

### Step 2: 
Read the input image using cv2.imread() and store it in a variable.

### Step 3: 
Display the original image using Matplotlib to verify that the image is loaded correctly.

### Step 4:
Perform Image Translation by defining a translation matrix and applying cv2.warpAffine() to shift the image.

### Step 5: 
Perform Image Scaling and Shearing by resizing the image using cv2.resize() and applying a shear matrix using cv2.warpAffine().

### Step 6: 
Perform Image Reflection and Rotation using cv2.flip() for reflection and cv2.getRotationMatrix2D() with cv2.warpAffine() for rotation.

### Step 7: 
Perform Image Cropping by selecting a specific region of the image using slicing and display all transformed images.

## Program:
```python
Developed By: Rithika L
Register Number:212224230231
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('Chennai_Central.jpg')
image.shape
# Display the images.
plt.imshow(image[:,:,::-1])
plt.title('Original Image')
plt.show()
```
### i)Image Translation
```python
tx, ty = 100, 200  
M_translation = np.float32([[1, 0, tx], [0, 1, ty]])  

translated_image = cv2.warpAffine(image, M_translation, (301, 167)) 
plt.imshow(translated_image[:,:,::-1])
plt.title("Translated Image")
plt.axis('on')
plt.show()
```
### ii) Image Scaling
```python
fx, fy = 2.0, 1.0  
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)
plt.imshow(scaled_image[:,:,::-1]) 
plt.title("Scaled Image") 
plt.axis('on')
plt.show()
```




### iii)Image shearing
```python
shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  
sheared_image = cv2.warpAffine(image, shear_matrix, (301, 167))
plt.imshow(sheared_image[:,:,::-1])
plt.title("Sheared Image") 
plt.axis('on')
plt.show()
```



### iv)Image Reflection
```python
reflected_image = cv2.flip(image, 2)  
# Show original image 
plt.figure(figsize=(10, 5))

plt.subplot(1, 2, 1)
plt.imshow(image[:, :, ::-1])
plt.title("Original Image")
plt.axis('off')

# Show reflected image 
plt.subplot(1, 2, 2)
plt.imshow(reflected_image[:,:,::-1])
plt.title("Reflected Image")
plt.axis('off')

plt.tight_layout()
plt.show()
```





### v)Image Rotation
```python
(height, width) = image.shape[:2]  
angle = 45  
center = (width // 2, height // 2)  
M_rotation = cv2.getRotationMatrix2D(center, angle, 1)  
rotated_image = cv2.warpAffine(image, M_rotation, (width, height))  
plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB))  
plt.title("Rotated Image") 
plt.axis('off')
```
```python
angle = 145  
center = (301 // 2, 167 // 2)  
M_rotation = cv2.getRotationMatrix2D(center, angle, 1)  
rotated_image = cv2.warpAffine(image, M_rotation, (width, height)) 
plt.imshow(rotated_image[:,:,::-1])  
plt.title("Rotated Image")  
plt.axis('off')
plt.show()
```





### vi)Image Cropping
```python
x, y, w, h = 0, 0, 150, 100  

cropped_image = image[y:y+h, x:x+w]  
# Show original image 
plt.figure(figsize=(10, 5))

plt.subplot(1, 2, 1)
plt.imshow(image[:, :, ::-1])
plt.title("Original Image")
plt.axis('on')

# Show reflected image 
plt.subplot(1, 2, 2)
plt.imshow(cropped_image[:,:,::-1])
plt.title("Cropped Image")
plt.axis('on')

plt.tight_layout()
plt.show()






```
## Output:
### i)Image Translation
<br>
<br>
<br>
<br>

### ii) Image Scaling
<br>
<br>
<br>
<br>


### iii)Image shearing
<br>
<br>
<br>
<br>


### iv)Image Reflection
<br>
<br>
<br>
<br>



### v)Image Rotation
<br>
<br>
<br>
<br>



### vi)Image Cropping
<br>
<br>
<br>
<br>




## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
