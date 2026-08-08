# Implementation of Image Filters Using OpenCV

---

## Aim

To write a Python program using OpenCV to implement various image filtering techniques on a given image.

The program performs the following operations:

- Averaging Filter
- Gaussian Filter
- Gaussian Blur
- Median Blur
- Custom Filter
- Laplacian Operator

---

# Software Used

- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- OpenCV (`cv2`)
- NumPy
- Matplotlib

---

# Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the input image (`thamizh.jpg`) using `cv2.imread()` and convert it from BGR to RGB format.

### Step 3: Averaging Filter
- Create an **11 × 11 averaging kernel**.
- Apply the filter using `cv2.filter2D()`.
- Display the original and filtered images.

### Step 4: Gaussian Filter
- Create a **3 × 3 Gaussian kernel**.
- Apply the filter using `cv2.filter2D()`.
- Display the output image.

### Step 5: Gaussian Blur
- Apply Gaussian Blur using `cv2.GaussianBlur()`.
- Use a kernel size of **33 × 33**.
- Display the blurred image.

### Step 6: Median Blur
- Apply Median Blur using `cv2.medianBlur()`.
- Use a kernel size of **13**.
- Display the filtered image.

### Step 7: Custom Filter
- Create a custom convolution kernel.
- Apply the filter using `cv2.filter2D()`.
- Display the filtered output.

### Step 8: Laplacian Operator
- Apply the Laplacian operator using `cv2.Laplacian()`.
- Display the edge-detected image.

---

# Program

### Developed By

**Name:** Thamizh S

**Register No:** 212224040350

---

# Code

```python
import cv2
import matplotlib.pyplot as plt
import numpy as np

# Read Image
image1 = cv2.imread("thamizh.jpg")
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

# ----------------------------
# Averaging Filter
# ----------------------------
kernel = np.ones((11,11), np.float32)/169
image3 = cv2.filter2D(image2,-1,kernel)

plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter")
plt.axis("off")
plt.show()

# ----------------------------
# Gaussian Filter
# ----------------------------
kernel1 = np.array([[1,2,1],
                    [2,4,2],
                    [1,2,1]])/16

image3 = cv2.filter2D(image2,-1,kernel1)

plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Gaussian Filter")
plt.axis("off")
plt.show()

# ----------------------------
# Gaussian Blur
# ----------------------------
gaussian_blur = cv2.GaussianBlur(image2,(33,33),0,0)

plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()

# ----------------------------
# Median Blur
# ----------------------------
median = cv2.medianBlur(image2,13)

plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Median Blur")
plt.axis("off")
plt.show()

# ----------------------------
# Custom Filter
# ----------------------------
kernel2 = np.array([[-1,-1,-1],
                    [2,-2,1],
                    [2,1,-1]])

image3 = cv2.filter2D(image2,-1,kernel2)

plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Custom Filter")
plt.axis("off")
plt.show()

# ----------------------------
# Laplacian Operator
# ----------------------------
laplacian = cv2.Laplacian(image2,cv2.CV_64F)

plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1,2,2)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```

---

# Output

### Original Image

<img width="432" height="503" alt="image" src="https://github.com/user-attachments/assets/0940dc86-ee67-44ef-872c-e7f99ed5eee1" />


### Averaging Filter

<img width="428" height="445" alt="image" src="https://github.com/user-attachments/assets/c7768a43-352f-4144-b7ee-5fbfc1820519" />


### Weighted Average Filter Image

<img width="329" height="299" alt="image" src="https://github.com/user-attachments/assets/702be333-6d08-47dc-aaa4-96b46dd617a5" />


### Gaussian Blur

<img width="322" height="321" alt="image" src="https://github.com/user-attachments/assets/c97cbc0b-0b1e-4696-b043-bf5536b8c2a7" />

### Median Blur

<img width="438" height="449" alt="image" src="https://github.com/user-attachments/assets/2e51d586-63b2-43cf-9cfd-8c299729401c" />

### Laplacian Kernel

<img width="401" height="335" alt="image" src="https://github.com/user-attachments/assets/99bbde2c-adc5-4fbb-8eee-4564d59500c0" />

### Laplacian Operator

<img width="311" height="309" alt="image" src="https://github.com/user-attachments/assets/5dfbe4ce-2b37-4e9c-98c7-732665913379" />

---

# Result

Thus, the various image filtering techniques such as **Averaging Filter, Gaussian Filter, Gaussian Blur, Median Blur, Custom Filter, and Laplacian Operator** were successfully implemented using OpenCV. The output images demonstrate the effectiveness of different filtering methods for smoothing, noise reduction, and edge detection in digital image processing.
