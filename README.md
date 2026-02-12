# Histogram-of-an-images
## NAME :Madhan C
## REGISTER NUMBER : 212224240081

## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read the gray and color image using imread()

### Step2:
Print the image using imshow().



### Step3:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### step4:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### Step5:
The Histogram of gray scale image and color image is shown.


## Program:
```python
#import the libraries 
import cv2
from matplotlib import pyplot as plt

# Load the color image
image = cv2.imread(r"23.jpg.jpeg")

# Check if the image was loaded successfully
if image is None:
    print("Error: Image not found or path is incorrect.")
else:
    # Convert the image to grayscale
    gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

    # Display the grayscale image
    plt.figure(figsize=(6, 6))
    plt.imshow(gray_image, cmap='gray')
    plt.title('Original Grayscale Image')
    plt.axis('off')
    plt.show()

# Calculate histogram for the original grayscale image
hist_original = cv2.calcHist([gray_image], [0], None, [256], [0, 256])

# Plot the histogram
plt.figure(figsize=(6, 4))
plt.plot(hist_original, color='black')
plt.title('Original Histogram')
plt.xlabel('Pixel Intensity')
plt.ylabel('Frequency')
plt.xlim([0, 256])
plt.grid(True)
plt.show()

# Apply histogram equalization
equalized_image = cv2.equalizeHist(gray_image)

# Display the equalized grayscale image
plt.figure(figsize=(6, 6))
plt.imshow(equalized_image, cmap='gray')  # corrected colormap spelling
plt.title('Equalized Image')
plt.axis('off')
plt.show()

# Calculate histogram for the equalized image
hist_equalized = cv2.calcHist([equalized_image], [0], None, [256], [0, 256])

# Plot the histogram
plt.figure(figsize=(6, 4))
plt.plot(hist_equalized, color='black')
plt.title('Equalized Histogram')
plt.xlabel('Pixel Intensity')
plt.ylabel('Frequency')
plt.xlim([0, 256])
plt.grid(True)
plt.show()
```
## Output:
### Input Grayscale Image and Color Image

<img width="462" height="600" alt="image" src="https://github.com/user-attachments/assets/27e7dc9c-3c44-411f-877b-8dd01fd5086c" />


### Histogram of Grayscale Image and any channel of Color Image

<img width="748" height="461" alt="image" src="https://github.com/user-attachments/assets/80f60485-a59e-46d5-9096-77d935e86af1" />


### Histogram Equalization of Grayscale Image.

<img width="480" height="605" alt="image" src="https://github.com/user-attachments/assets/4f77bf3a-b4f4-40ec-8ff3-460b04aad784" />
<img width="702" height="467" alt="image" src="https://github.com/user-attachments/assets/48d24967-078d-41a4-9d49-eae922938581" />



## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
