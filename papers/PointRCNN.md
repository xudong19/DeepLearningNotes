[PointRCNN: 3D Object Proposal Generation and Detection from Point Cloud](https://arxiv.org/pdf/1812.04244.pdf) [CVPR 19]
---------------	

__TL;DR__: This paper extend the RCNN idea in image object detection into point cloud. 

__keywords__: OD, PC

__Resources__: [[Github](https://github.com/sshaoshuai/PointRCNN)] 

__Other Notable Info__: 

<br/>    

General Comments:
------
* The idea is straightforward. First using the point-cloud processing modules (e.g. pointnet++) to extract feature. And then
use every forground points (after a binary point segmentation module) to generate bounding box proposals. At the second stage,
the apply box refinement to the box proposals.


Key ideas and technical details:
------
* Using pointnet++ to extract high-level semantic features for each point. 
* Applying point-wise segmentation to segment the point-cloud to be foreground (within interested instances) and background.
* Use all the forground points to generate 3D bounding box proposals. And then consolidate proposals by NMS and top 300 proposals.
* Then apply bounding box refinement based on the bounding box proposals.

Other noteworthy points:
------
* In the second stage, all the points are transformed into canonical coordinate (instance-specific) for the further refinement.


