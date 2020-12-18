# Lane-Detection
Lane detection for self driving cars

The goal of this project is to exactly detect the lanes on a road to understand how self driving cars 
"see" when they are moving on the road.

## Edge detection

The reason we perform edge detection is to identify the boundaries of objects in an image.Therefore we try to find 
the areas in an image where there is a sharp change in intensity and a sharp change in color. 

### Gray-scale image

The gray-scale image image has only one pixel intensity value (0 or 1) compared to a colored image which has 
more than three values. This will make the gray-scale image to work in a single channel, which will be easier for us
to process rather than three channeled color picture.

[](https://i.imgur.com/tHxRIbz.png)