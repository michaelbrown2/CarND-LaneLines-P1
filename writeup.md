 #**Finding Lane Lines on the Road** 

##Michael Brown

###Project one of CarND - Lane Lines

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"
[image2]: ./example/original.jpg "Original"
[image3]: ./example/gradient.jpg "Gradient"
[image4]: ./example/gaussian.jpg "Gaussian"
[image5]: ./example/masked.jpg "Masked"
[image6]: ./example/hough.jpg "Hough"
[image7]: ./example/final.jpg "Final"


---

### Reflection

###1. Pipeline

The pipeline I use does the following:

1. Convert to grayscale
2. Apply Canny translation
3. Apply Gaussian translation
4. Mask off area of interest
5. Process Hough lines on image
6. Takes Hough line end points and slope of all similar lines to generate average slope and a generic line through down to the bottom (origin, or car in this case) of the image
7. Draw those lines on the image

The draw_lines function was modified to calculate average slope and make a line that would connect the furthest top point of a confirmed 'line' down to the origin using the average slope of all lines found.

I attempted to modify pipe line to deal with Challenge video, however changes I made to compensate for it made the base videos unreliable in processing. 

####Example from pipe line

![alt text][image2]
![alt text][image3]
![alt text][image4]
![alt text][image5]
![alt text][image6]
![alt text][image7]


###2. Shortcomings


1. Jitter
2. The ability to deal with curved lines


###3. Suggest possible improvements to your pipeline

1. A better method of averaging the points in the line would make the jitter more managable
2. Rework line making algorithm to compensate for curved lines.
3. Tune settings to be more forgiving with shady areas and less drastic color changes.
4. Hopefully with above changes, the challenge video will process as well.
