[medium](https://dev.to/andreygermanov/how-to-implement-instance-segmentation-using-yolov8-neural-network-3if9)
The result of the instance segmentation is a segmentation mask of each detected object. The segmentation mask is a black-white image, on which all pixels that belong to the object are white, and all other pixels are black.
![mask](https://res.cloudinary.com/practicaldev/image/fetch/s--D-BBqeKp--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/rkzs89knnz12rrkm7252.png)

Furthermore, having these bit masks of detected objects, you can calculate their contours
![contour](https://res.cloudinary.com/practicaldev/image/fetch/s--wJHZJtGx--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/b4muzf9070ezu1atrphi.png)

The calculated contour is a polygon, which is an array of point coordinates. This polygon can be used to identify the detected objects on images in real world applications much more precisely than just using the bounding boxes.