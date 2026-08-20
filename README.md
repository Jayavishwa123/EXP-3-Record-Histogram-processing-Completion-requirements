# EXP-3-Record-Histogram-processing-Completion-requirements
# Aim
To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

Read and display a grayscale image
Plot histogram of the grayscale image
Apply histogram equalization on grayscale image
Read and display a color image
Plot histogram of B, G, R channels
Convert image to HSV color space
Apply histogram equalization on the Value (V) channel
Convert the enhanced image back to BGR format
Display original and enhanced images with histograms
# Software Used
Anaconda – Python 3.7

Jupyter Notebook / VS Code

OpenCV (cv2)

NumPy

Matplotlib

# Algorithm
Step 1: Import the required libraries: OpenCV, NumPy, and Matplotlib.

Step 2: Read the image parrot.jpg in grayscale format.

Step 3: Display the grayscale image and plot its histogram.

Step 4: Apply histogram equalization using cv2.equalizeHist() to enhance contrast.

Step 5: Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

Step 6: Read the same image in color format.

Step 7: Split the image into B, G, R channels and plot their histograms.

Step 8: Convert the image from BGR to HSV color space.

Step 9: Apply histogram equalization on the V (Value) channel.

Step 10: Merge the channels and convert the image back to BGR format.

Step 11: Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.

# Program
Developed By: Name: Jaya Vishwa S
Register No:212224230105
```
img = cv2.imread('sec.jpg', cv2.IMREAD_GRAYSCALE)
plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()
```
<img width="762" height="848" alt="image" src="https://github.com/user-attachments/assets/8c5e0c61-3349-470f-bcf1-908ef98dfba4" />

```
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
```
<img width="856" height="592" alt="image" src="https://github.com/user-attachments/assets/b1f50975-f4bf-4e52-a11a-282f76632a72" />

```
img_eq = cv2.equalizeHist(img)
plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')
```
<img width="802" height="666" alt="image" src="https://github.com/user-attachments/assets/06ceeca1-a19c-4ffd-a73f-6edbe944b954" />

```
plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()
```
<img width="695" height="590" alt="image" src="https://github.com/user-attachments/assets/daffa410-e601-4f39-8cce-11f14785fbc1" />

```
img = cv2.imread('sec.jpg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()
```
<img width="693" height="768" alt="image" src="https://github.com/user-attachments/assets/59cc5c57-495f-4823-8f20-8aa1e5567fac" />

```
plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()
```
<img width="842" height="543" alt="image" src="https://github.com/user-attachments/assets/62a9af7b-5065-49a8-ae9a-5554b9f0769b" />

```
plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()
```
<img width="1309" height="505" alt="image" src="https://github.com/user-attachments/assets/7de79369-6611-4cf8-9a41-10554af80eb4" />

```
plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```
<img width="1289" height="508" alt="image" src="https://github.com/user-attachments/assets/16450624-3c33-4096-9a18-fd0d04cbd6bc" />

# Result
Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
