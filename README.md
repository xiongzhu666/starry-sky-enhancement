# starry-sky-enhancement
##This algorithm is designed to enhance the effect of astrophotography during long exposure mode.

When taking pictures of the starry sky with a phone, due to the small photosensitive area and limited ability of the phone sensor, the exposure value needs to be increased (such as more than 3 minutes of exposure time). However, in doing so, the stars in the photos may produce a trailing effect.

![compare](https://github.com/xiongzhu666/starry-sky-enhancement/blob/main/compare.png)

By zooming in on local areas, it is easy to see that the trailing effect of stars has been eliminated and the brightness of stars is higher than that of the original photo. With this algorithm, we have overcome the limitations of phone camera sensors and greatly improved the quality of astrophotography taken with phones.

![look](https://github.com/xiongzhu666/starry-sky-enhancement/blob/main/look.png)

The algorithm works as follows:
1. Segment the sky area of the image to obtain a mask of the sky region. The method can refer to my other repository: https://github.com/xiongzhu666/Sky-Segmentation-and-Post-processing
2. Use line detection algorithm to detect the lines in the sky region of the image. Extract the brightness values and RGB values of the pixels on the detected lines.
3. Fill in the pixels around the line pixels to eliminate the lines.
4. Sort the brightness values extracted in step 2, fill in the brightest pixel values at the center of the line, and fill in the pixels with lower brightness in a circular pattern around the center of the line.
