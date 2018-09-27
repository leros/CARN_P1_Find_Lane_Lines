# **Finding Lane Lines on the Road** 
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)
---
Overview
---

When we drive, we use our eyes to decide where to go.  The lines on the road that show us where the lanes are act as our constant reference for where to steer the vehicle.   Naturally, one of the first things we would like to do in developing a self-driving car is to automatically detect lane lines using an algorithm. In this project I detect lane lines in images using Python and OpenCV. 

### Pipeline
![Original Image](./test_images/solidWhiteCurve.jpg)
The orignial image is shown above. My pipeline consisted of 6 steps as follows.

1. converted the images to grayscale <br>
![Gray](./pipeline/1-Gray.png)
2. applied gaussian smoothing<br>
![Blur](./pipeline/2-Gaussian_Blur.png)
3. detected edges<br>
![Canny](pipeline/3-Canny.png)
4. created a masked edges image<br>
![Mask](./pipeline/4-Mask.png)
5. detected lines<br>
![Hough](./pipeline/5-Hough.png)
6. drew lines on the original image<br>
![Output](./pipeline/6-Output.png)

### Improvement on draw_lines() function
First, I identified all the segments on the left side and all the segments on the right side. Then I figured out two lines that fitted those segments, one for the left line and the other for the right line. With the modified draw_lines() function, the processed image would look like this.<br>
![example](./pipeline/draw_line_plus_example.png)

### Potential shortcomings with current pipeline


One potential shortcoming would be what would happen when the road is not straight, e.g. at detour or roundabout. Now the pipeline only handles straight lines.

Another shortcoming could be that when the lines are not clear or obvious it would be hard to tell where the lines are.


### Suggest possible improvements to the pipeline

A possible improvement would be to improve the line detection so that curves could be
found.

Another potential improvement could be enhancing the detected edges so that the pattern of lines are more obvious and can be easily detected.
