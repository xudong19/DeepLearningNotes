[3DSSD: Point-based 3D Single Stage Object Detector](https://arxiv.org/pdf/2002.10187.pdf) [CVPR 20]
---------------	

__TL;DR__: This paper greatly facilitated the point-based object detection method by removing 
feature propagation (FP, aka. upsampling) layer and simplifying the detection head.

__keywords__: OD, PC

__Resources__: [[Github](https://github.com/Jia-Research-Lab/3DSSD)] 

__Other Notable Info__: 

<br/>    

General Comments:
------
* The point-based methods are generally slower than image-based methods. By dissecting PointRCNN, the paper find the FP
layer and the prediction refinement layer takes a lot of time. 
* This paper attempted to remove the FP layer by improving the point downsampling process. And also simplify the detection head
into one stage.

Key ideas and technical details:
------
* The improved downsampling process to promote recall by using feature distance instead of physical position distance.
* The sample fusion method to use the farthest distance sampling method to increase the receptive field and gather enough negative points.
* The direct boudning box prediction from candidate points. The use of centerness prediction as the classification loss instead of conventional
cross-entropy loss.

Other noteworthy points:
------
* The representive points are first shifted to the center of each instance before being used for regression. In this way,
the centerness score is more balanced. 
* The additional corner position loss despite that the corners are not directly regressed.


