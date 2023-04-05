# Histogram and Histogram Equalization of an image
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
### Step4:
cv2.equalize() is used to transform the gray image to equalized form.
### Step5:
The Histogram of gray scale image and color image is shown.


## Program:

### Developed By: Senthil Kumar S
### Register Number: 212221230091
```python
# Code to find the histogram of gray scale image and color image channels.
import cv2
import matplotlib.pyplot as plt

gray=cv2.imread("eren.jpg",0)
gray= cv2.resize(gray, (904,507))
cv2.imshow('gray image',gray)

color=cv2.imread("aot.jpg",1)
color= cv2.resize(color, (727,403))
cv2.imshow('color image',color)

cv2.waitKey(0)
cv2.destroyAllWindows()

# Display the histogram of gray scale image and any one channel histogram from color image
gray_hist=cv2.calcHist([gray],[0],None,[256],[0,255])
color_hist=cv2.calcHist([color],[2],None,[256],[0,255])

plt.figure()
plt.title("gray image")
plt.xlabel("grayscale value")
plt.ylabel("pixel count")
plt.stem(gray_hist)
plt.show()

plt.figure()
plt.title("color image")
plt.xlabel("colorscale value")
plt.ylabel("pixel count")
plt.stem(color_hist)
plt.show()


# Code to perform histogram equalization of the image. 
gray_equalized=cv2.equalizeHist(gray)

cv2.imshow('gray image',gray)
cv2.imshow('equalized gray image',gray_equalized)
cv2.waitKey(0)
cv2.destroyAllWindows()

```
## Output:
### Input Grayscale Image and Color Image
![gray image](https://user-images.githubusercontent.com/93860256/230092801-04055d9b-f996-421b-9b84-c4a2cb129043.png)
![color image](https://user-images.githubusercontent.com/93860256/230092788-91928378-8e76-49a0-be40-ea9ecb1d1fcf.png)

### Histogram of Grayscale Image and any channel of Color Image
![histo](https://user-images.githubusercontent.com/93860256/230092804-021a3044-a4f6-4e51-9700-39f926e6dcb8.jpg)

### Histogram Equalization of Grayscale Image
![equalized gray image](https://user-images.githubusercontent.com/93860256/230092806-f8f7563c-c046-408f-8f17-67e80ca86afa.png)
![gray image](https://user-images.githubusercontent.com/93860256/230092801-04055d9b-f996-421b-9b84-c4a2cb129043.png)

## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
