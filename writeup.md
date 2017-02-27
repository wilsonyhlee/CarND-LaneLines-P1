#**Finding Lane Lines on the Road** 

##Writeup

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

###1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consists four steps:
1. Separate left and right lanes based on slope. Left lane has negative slope; right lane has positive slope.
2. For each lane, find best fit line through linear regression.
3. Adjust the best fit line based on line from the previous frame in order the make the video output smooth. The new line is ignored if it deviates too much from the previous frame.
4. Draw the lanes. 

###2. Identify potential shortcomings with your current pipeline
1. As of Feb 26, this implementation does not perform well on the optional challenge video (i.e. videos with curves). 
2. I implement a conditinoal in the pipeline to ignore best fit line parameters that deviate too much from those of the previous frame. This can cause issue when the car is making sharp turns on a hairpin turn. 

###3. Suggest possible improvements to your pipeline
1. Fit the data points from edge detection to a curve instead of a straight line to accomodate curvy lanes.  
2. Implement a more robust frame-to-frame conditional so that the pipeline will perform well on lanes with various curvature. 

