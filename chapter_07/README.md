# Chapter 7 Object detection with R-CNN, SSD, and YOLO
## Summary
1. Image classification is the task of predicting the type or class of an object in an image.
1. Object detection is the task of predicting the location of objects in an image via bounding boxes and the classes of the located objects.
1. The general framework of object detection systems consists of four main components: region proposals, feature extraction and predictions, non-maximum suppression, and evaluation metrics.
1. Object detection algorithms are evaluated using two main metrics: frame per second (FPS) to measure the network’s speed, and mean average precision (mAP) to measure the network’s precision.
1. The three most popular object detection systems are the R-CNN family of networks, SSD, and the YOLO family of networks.
1. The R-CNN family of networks has three main variations: R-CNN, Fast R-CNN, and Faster R-CNN. R-CNN and Fast R-CNN use a selective search algorithm to propose RoIs, whereas Faster R-CNN is an end-to-end DL system that uses a region proposal network to propose RoIs.
1. The YOLO family of networks include YOLOv1, YOLOv2 (or YOLO9000), and YOLOv3.
1. R-CNN is a multi-stage detector: it separates the process to predict the objectness score of the bounding box and the object class into two different stages.
1. SSD and YOLO are single-stage detectors: the image is passed once through the network to predict the objectness score and the object class.
1. In general, single-stage detectors tend to be less accurate than two-stage detectors but are significantly faster.