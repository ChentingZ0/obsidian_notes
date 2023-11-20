Labeled data highlights data features or properties, characteristics, or classifications that can be analyzed for patterns that help predict the target.
### Image Annotation Types
#### Bounding boxes
Bounding boxes are usually represented by either two coordinates (x1, y1) and (x2, y2) or by one co-ordinate (x1, y1) and width (w) and height (h) of the bounding box.

#### Polygonal Segmentation

#### Semantic Segmentation
Semantic segmentation is a pixel wise annotation, where every pixel in the image is assigned to a class.
 
Semantic Segmentation is primarily used in cases where environmental context is very important.

#### Landmarks



### Image Annotation Format
#### COCO
**COCO:** COCO has five annotation types: for object detection, keypoint detection, stuff segmentation, panoptic segmentation, and image captioning. The annotations are stored using JSON.
#### Pascal VOC
Pascal VOC stores annotation in XML file.
![Pascal VOC](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*ugjb3AmGBrWi3laJuwI0ug.png)

#### YOLO labeling format
[good article](https://medium.com/analytics-vidhya/image-dataset-labeling-annotation-bec3390eda2d)
[label_tool](https://roboflow.com/?ref=ultralytics)

![yololabel](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*MCbCwT5GuVzgK_wbeYe-vA.png)

YOLO label file contains 5 values. 
The 1st value is that of the class index id as it was mentioned in the class_list.txt file.

The remaining 4 values in the file are object coordinates and the height and width of the bounding box.

The label file will contain normalized values for all 5 parameters so their values will be between 0 to 1. The label for one object looks like as shown below.
`<object-class> <x_center> <y_center> <width> <height>`
Where:
- `<object-class>` - integer number for an object from `**0**` to `**(classes-1)**`
- `<x_center> <y_center> <width> <height>` - float values relative to width and height of the image, will be between 0.0 to 1.0
- for example: `<x> = <absolute_x> / <image_width>` or `<height> = <absolute_height> / <image_height>`
- attention: `<x_center> <y_center>` - are the center of the rectangle (not top-left corner)





### Questions
- One annotation tool:  https://www.cvat.ai/
- OpenLabeling

Questions:
1. Does all the images have to be labelled manually?
Training a YOLO model requires a labeled dataset with bounding boxes around the objects of interest.

2. Does YOLO and U-Net has its own corresponding label types?
U-Net requires a labeled dataset for training, where the labels are typically pixel-wise masks that delineate the boundaries of the objects or regions of interest within the images.

https://www.youtube.com/watch?v=m9fH9OWn8YM&ab_channel=Computervisionengineer: Manually labeling through AI tools
