# YOLO-Object-Detection-with-OpenCV
Object detection using YOLO object detector

### Detect objects in videos using Deep Learning, OpenCV, and Python.

I'll use YOLOv3 in this project, in particular, YOLO trained on the COCO dataset.

The COCO dataset consists of 80 labels, including, but not limited to:

- People
- Bicycles
- Cars and trucks
- Airplanes
- Stop signs and fire hydrants
- Animals, including cats, dogs, birds, horses, cows, and sheep, to name a few
- Kitchen and dining objects, such as wine glasses, cups, forks, knives, spoons, etc.
…and much more!

You can find the full list of what YOLO trained on the COCO dataset can detect <a href="https://github.com/pjreddie/darknet/blob/master/data/coco.names" target="_blank"><b>using this link.</b></a>

- yolo-coco : The YOLOv3 object detector pre-trained (on the COCO dataset) model files. These were trained by the <a href="https://pjreddie.com/darknet/yolo/" target="_blank"> <b>Darknet team.</b> </a>

- yolo-coco/yolov3.weights : You can download yolov3.weights <a href="https://pjreddie.com/media/files/yolov3.weights">here</a>

## YOLO object detection in video streams

## Installation

- `pip install numpy`
- `pip install opencv-python`
- `pip install imutils`

## To Run the project

- `python yolo_video.py --input videos/airport.mp4 --output output/airport_output.avi --yolo yolo-coco`

## Screenshots
![Image](/car.gif)

In the video/GIF, you can see not only the vehicles being detected, but people, as well as the traffic lights, are detected too!

The YOLO object detector is performing quite well here. 

## Limitation:
### Arguably the largest limitation and drawback of the YOLO object detector is that:

- It does not always handle small objects well.
- It especially does not handle objects grouped close together.
- The reason for this limitation is due to the YOLO algorithm itself:

The YOLO object detector divides an input image into an SxS grid where each cell in the grid predicts only a single object.
If there exist multiple, small objects in a single cell then YOLO will be unable to detect them, ultimately leading to missed object detections.
Therefore, if you know your dataset consists of many small objects grouped close together then you should not use the YOLO object detector.

In terms of small objects, Faster R-CNN tends to work the best; however, it’s also the slowest.

SSDs can also be used here; however, SSDs can also struggle with smaller objects (but not as much as YOLO).

SSDs often give a nice tradeoff in terms of speed and accuracy as well.