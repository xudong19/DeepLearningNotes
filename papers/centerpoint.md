[Center-based 3D Object Detection and Tracking](https://arxiv.org/pdf/2006.11275.pdf) [CVPR 20]
---------------	

__TL;DR__: This paper is a general extension of the centernet to the point-cloud domain. The paper first encode the point
clouds into BEV images (using classic PointPillars and VoxelNet), and then apply centernet object detection method directly 
onto the encoded BEV images.

__keywords__: OD, PC

__Resources__: [[Github](https://github.com/tianweiy/CenterPoint)] 

__Other Notable Info__: 

<br/>    

General Comments:
------
* The idea is pretty straightforward. It first encode point cloud into BEV images and then use centernet for object detection.
* This paper really shows the applicability of the centernet architecture in various scenarioes.



Key ideas and technical details:
------
* There are a few critical adaptions from the original centernet paper, to make it really work with point cloud. 
* Since most of regions in BEV are background, the supervision signal in heatmap is very sparse. So the auother enlarged 
the gaussian kernal to produce more positive supervision signals.
* The deformable convolution is used in the detection head to assist the rotated box prediction. The center prediction branch
and regression prediction branch are separated for that the center branch need to be rotationally invariant while the regression
branch need to be rotationally variant.
* The flip test-time augmentation are used to ensemble the output boxes.

Other noteworthy points:
------
* Very aggressive data augmentations are used during training. This seems to be a normal practice in point cloud object detection field.
* The balanced sampling and class grouped head ((CBGS)[https://arxiv.org/pdf/1908.09492.pdf]) is used. 


