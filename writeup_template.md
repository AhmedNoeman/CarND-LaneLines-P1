# **Finding Lane Lines on the Road** 

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale after specifying the region of interest,
then I converted the image to hsv and retrieved lanes of the yellow colour or white. Then a bitwise operation is applied on the colour and gray scale image 
to define the region of interest. Afterwards, applying gaussian blur and canny edge detection
to the resultant image. Finally, applying the hough transform to extract the lines.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by filtering lines based on slope and image quadrant
Classifying left and right lane associations by negative or positive slopes.

### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when is when the ego car is faced by pedastrian crossings marks. 

Another shortcoming could be when a target car is too close to the ego vehicle so only a small portion of the lanes appear.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to estimate the positions of the lanes via prediction and update (Kalman filter) 
