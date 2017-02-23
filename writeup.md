#**Finding Lane Lines on the Road** 

##Writeup 


Van Tri Tin Tran
tritini@gmail.com

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

###1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I used Canny to detect edges. Then i chose the region of interest and masked it to remove noise. Then i used Hough transform to find lines in this region. Because there are lines not connected and discrete, i must add one function to connect the discrete lines into one line. Finally, i have only detected left line and right line.    

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by using slope of every line on set of lines to find which line belongs to the left side or right side. Then i calculate the slope average and intercept average of left line and right line, in which i used length of line as a factor to determine the impact on direction of line.

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image_result.png]


###2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when the car goes into curve. 

Another shortcoming could be the capability of recognize the lane line when it is dashed and have big interval between lines segment found it during Hough transform.

Another shortcoming could be the drawback when the car is in the evening and it is not under good weather.

###3. Suggest possible improvements to your pipeline

A possible improvement would be to process the video better because there is still jitter.

Another potential improvement could be to find ways to make extrapolation between lines better.