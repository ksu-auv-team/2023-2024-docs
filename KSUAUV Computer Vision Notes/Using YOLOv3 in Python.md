Notes on achieving [[Computer Vision]] with [[YOLOv8]] in [[Python 1]]. Notes are taken from [this video](https://www.youtube.com/watch?v=b59xfUZZqJE).

# First, Working with OpenCV.
The images are pre-processed by the [[OpenCV]] library before they are sent to the YOLO model to be classified. 
## Grabbing and Displaying
Here's an example of simply grabbing and displaying an image, using `imread()` and `imshow()`.
```Python
import cv2 #OpenCV
import matplotlib.pyplot as plt #For displaying on cloud editors
import numpy as np #Used by OpenCV for arrays of pixels.

#push an image to be processed by cv2
#image = cv2.imread("someurl")
image = cv2.imread("https://as1.ftcdn.net/jpg/02/95/94/94/220_F_295949484_8BrlWkTrPXTYzgMn3UebDl1O13PcVNMU.jpg")

#If imread() successful grabbed the object, this will return "numpy.ndarray", an array of fixed-size, same type items. If it did not, it will return <class:NoneType>. This is good for checking for reading errors.
type(image)

#This will return a tuple containing the dimensions of the array;
#(Height, width, color channels(usually RGB, so 3))
image.shape

#OpenCV has it's own display method, but it doesn't work on cloud-based platforms.
#It will open a window with the name of the string passed to it.
imshow('cat!', image)

#You can use matplotlib to display the image in a graph in Google Colab.
plt.imshow(image)
```
## Color-Converting
The `imread()` function reads colors in BGR order, which when displayed to RGB screens causes the colors to invert. To reverse this, use the `cv2.cvtColor()` method.
```Python
#Reverse the image's color channels from BGR to RGB, then display it.
image_colorFixed = cv2.cvtColor(image, cv2.COLORBGR2RGB)
cv2.imshow('correctly colored cat!', imagecolorFixed)
```
## Splitting
You can split an image channel by channel by the `split()` method. Inversely, you can merge channels with `merge()`.
```python
r,g,b = cv2.split(image_colorFixed)

print(r.shape)

#Output: (width, height) with no channel component.

#Pass the function a tuple of the channels.
image_Merged = cv2.merge((r,g,b))
```
## Scaling
You can also scale down the images using `resize()`. In the arguments, you must specify the new dimensions in a tuple, and also the interpolation method.
```python
#Here is a function to scale down, given a scaling factor.
def ScaleImage(image, scale):
	width = int(image.shape[1]*s/100)
	height = int(image.shape[0]*s/100)
	dimensions = (width, height)
	return cv2.resize(image, dimensions, interpolation = cV2.INTER_AREA)
```
## Rotating
You can rotate an object using two methods in sequence; `getRotationMatrix2D()` which defines the rotation to be applied by it's center point, angle and any scaling, and `warpAffine()` which applies it to the image.
```python
#Applies a rotation from the image center. Uses degrees.
def RotateImageFromCenter_Deg(image, angle)
	(height, width) = image.shape[:2]
	
	center = (width/2, height/2)
	
	rotationMatrix = cv2.getRotationMatrix2D(center, angle) 
	return cv2.warpAffine(image, m, (height, width))
```


As you can see, there are many methods in the OpenCV library that make manipulating images easy.

# How CNN's Process Images
![[Convolution Neural Network]]
# The YOLO Algorithm
The YOLO algorithm works in a very different fashion than a CNN. 
# Implementing the YOLO Algorithm using OpenCV
```python
yolo = cv2.dnn.readNet("urlfortheyoloweights.weights","urlfortheyoloconfig.cfg")
```
YOLO is a pretrained model, meaning it ships with the ability to detect basic objects, included as part of the COCO benchmark test.   