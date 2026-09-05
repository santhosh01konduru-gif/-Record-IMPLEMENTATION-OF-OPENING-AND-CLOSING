# Opening and Closing Operations Using OpenCV
# NAME: KONDURU SANTHOSH
# REG.No: 212225240074

## Aim

To write a Python program using OpenCV to perform morphological Opening and Closing operations on an image.

The program performs the following operations:

- Morphological Opening
- Morphological Closing

## Software Used

- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- OpenCV (cv2)
- NumPy
- Matplotlib

## Algorithm

### Step 1:

Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:

Create or load an input image containing foreground objects.

### Step 3:

Display the original image.

### Step 4:

Create a structuring element (kernel) of suitable size.

### Step 5: Opening Operation

- Apply the Opening operation using the structuring element.
- Opening consists of Erosion followed by Dilation.
- Remove small foreground noises while preserving the shape of larger objects.
- Display the opened image.

### Step 6: Closing Operation

- Apply the Closing operation using the structuring element.
- Closing consists of Dilation followed by Erosion.
- Fill small holes and gaps within foreground objects.
- Display the closed image.

### Step 7:

Compare the original, opened, and closed images.


## PROGRAM
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
# Create a blank image
image = np.zeros((500, 500, 3), dtype=np.uint8)
# Add text on the image using cv2.putText
font = cv2.FONT_HERSHEY_SIMPLEX
cv2.putText(image, 'Hello Java', (100, 250), font, 1, (255, 255, 255), 2, cv2.LINE_AA)
# Create a simple square kernel (3x3)
kernel = np.ones((3, 3), np.uint8)
# Display the input image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for displaying
plt.title("Input Image with Text")
plt.axis('off')
# Opening is erosion followed by dilation
opened_image = cv2.morphologyEx(image, cv2.MORPH_OPEN, kernel)
# Display the result of Opening
plt.imshow(cv2.cvtColor(opened_image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB
plt.title("Opening Operation")
plt.axis('off')
# Closing is dilation followed by erosion
closed_image = cv2.morphologyEx(image, cv2.MORPH_CLOSE, kernel)
plt.imshow(cv2.cvtColor(closed_image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB
plt.title("Closing  Operation")
plt.axis('off')
```

### Original Image

<img width="585" height="471" alt="image" src="https://github.com/user-attachments/assets/ba1c7870-ccb0-4a8d-a2b2-f299ecaebfc3" />



### Opening Operation

<img width="575" height="457" alt="image" src="https://github.com/user-attachments/assets/4bf77448-444a-440f-b287-b6f8f9f95bfd" />



### Closing Operation

<img width="578" height="467" alt="image" src="https://github.com/user-attachments/assets/dffd4b1c-b1ad-4ecb-bc8d-e20fd85c41d1" />

## Applications

### Opening

- Noise removal in binary images.
- Separation of connected objects.
- Preprocessing for object detection.

### Closing

- Filling small holes in objects.
- Connecting nearby components.
- Enhancing segmented regions.

## Advantages

### Opening

- Removes unwanted foreground noise.
- Preserves major object structures.
- Improves segmentation quality.

### Closing

- Restores object continuity.
- Eliminates small background gaps.
- Improves object representation.

## Result

Thus, the morphological operations **Opening** and **Closing** are successfully implemented using OpenCV. 
