#5. Convolutional Neural Networks part 2

Limitations about trational CNN:

* Mostly on centered images
* Only a single object per image
* Not enough for many real world vision tasks:
  * Localisation
  * Object Detection
  * Semantic segmentation
  * Instance segmentation



## Localisation

* Single object per image
* Predict coordinates of a bounding box (x,y,w,h)
* Evaluate via IoU

![](https://ws2.sinaimg.cn/large/006tKfTcly1g1j4c9r2e2j31130u016j.jpg)



## Object detection

We don't know the number of objects in the image.

* Object proposal : find region of interest (ROIs) in the image
* Object classification : classify the object in these regions

Two main families:

* A grid in the image where each cell is a proposal (SSD, YOLO)
* Region proposal (SPP, MultiBox, Faster RCNN)



### YOLO

![](https://ws2.sinaimg.cn/large/006tKfTcly1g1j4hg39dyj316g0u01kx.jpg)



### SDD : single-shot detector

![](https://ws1.sinaimg.cn/large/006tKfTcly1g1j4isp2fzj31bv0u04fm.jpg)



### Box proposals

Instead of having a predefined set of box proposals, find them on the image:

* Selective search: from pixels (not learnt)
* Faster-RCNN : region proposal network(RPN)

**Crop-and-resize** operator (**Rol-Pooling**)



### Fast-RCNN



### Faster-RCNN



### State of the art

* comparison between different algo
* Mask RCNN, light-head R-CNN for best accuracy
* Yolo, SSD, Light-Head R-CNN for fast inference



## Segmentation

![](https://ws1.sinaimg.cn/large/006tKfTcly1g1j4t63yjjj31bh0u0b29.jpg)



### Mask R-CNN



### State of art

* Mask-RCNN and other architectures
* Focal loss, Feature Pyramid Networks, etc
* Retina Net
* MegDet









