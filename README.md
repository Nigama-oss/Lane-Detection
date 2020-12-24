# Lane-Detection

The goal of this project is to exactly detect the lanes on a road to understand how self driving cars 
"see" when they are moving on the road.

## Edge detection

The reason we perform edge detection is to identify the boundaries of objects in an image.Therefore we try to find 
the areas in an image where there is a sharp change in intensity and a sharp change in color. 

### Gray-scale image

The gray-scale image image has only one pixel intensity value (0 or 1) compared to a colored image which has  more than three values. This will make the gray-scale image to work in a single channel, which will be easier for us to process rather than three channeled color picture.

![](https://i.imgur.com/tHxRIbz.png)

### Finding lane lines

We do this by a method called 'Canny method' which comes with open CV. The resulting image is a gradient image which highlights only the edges, in which strong gradient represents a sharp change in color whereas small gradient represents a shallow change in color.

![](https://i.imgur.com/DmimzNo.png)

### Region of interest

I picked the region of interest to be the right side of the lane in the image, as shown in the picture below.

![](https://i.imgur.com/dXJbCZF.png)

To isolate this region, we use matplotlib library to exactly spot the co-ordinates that give us the exact positions of the lane. The resulting image is the same as previous one, but is generated with X and Y axes.

![](https://i.imgur.com/aQsC4mQ.png)

The goal now, is to generate an image that is completely black with the same dimensions of our road image, and fill part of its area with a triangular polygon that isolates only the region of interest. 

The image we get is a mask of the polygon with specified vertices from our original image.

![](https://i.imgur.com/7mz0rJM.png)

The above image is important to show only the specific region of our image. The remaining objects will be 'masked'. The next image will show only the areas traced by the polygon on the previous gradient image.

![](https://i.imgur.com/wd2b04y.png)

### Detecting lane lines

To detect the lane line from our original image, we use a method called [hough transform](https://towardsdatascience.com/lines-detection-with-hough-transform-84020b3b1549) which helps us to identify identify the vertical lines from X and Y co-ordinates. 

![](https://i.imgur.com/u7TR0hR.png)

## Detecting lanes in video

The same process is followed to detect lanes in a video. This is made easy by the 'VideoCapture' object by OpenCV. Thie object lets you read frame by frame and perform the operations that we need. 

![](https://i.imgur.com/3xQxJDD.gif)

## How to run

- Clone this repository.
- Install openCV from your terminal.
- Run `lanes.py`.

