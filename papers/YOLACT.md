[YOLACT: Real-time Instance Segmentation](https://arxiv.org/pdf/1904.02689.pdf) [ICCV 19]
[YOLACT++: Better Real-time Instance Segmentation](https://arxiv.org/pdf/1912.06218.pdf) [PAML 20]
---------------	

__TL;DR__: The paper propose a pretty noval way to do instance segmentation, which first generate prototypes (more like a 
global mask), and than for each object performing coefficient regression in addition to normal object detection. In this way,
each instance mask can be assembled from prototypes.

__keywords__: IS

__Resources__: [[Github](https://github.com/dbolya/yolact)]

__Other Notable Info__: 

<br/>    

General Comments:
------
* The method seems to be a mix between local method and global method. The normal bbox detection part is local method, yet the mask assembly part
is a global method.
* The prototypes and the mask coefficients are jointly trained, which brings the benefit of optimizing towards the gobal minimum, yet also leads to 
the drawback that it is hard to understand why the detector fails in some cases and how we should improve it in the ablation study.


Key ideas and technical details:
------
* The instance segmentation tasks can be viewed as two sub-problems, where the object is and what is the mask. This paper adapt contrastingly different approaches
to handle the two subproblems. Use traditional object detection framework to locate the object and use the very global method, coupled with the locally regressed 
coefficients to tackle the what is the mask problem.  
* The separated cls and reg branches in prediction head are combined together with the additional mask coefficient branch.
* Similar to the IoU/Centerness loss in object detection, the mask score loss can promote the performance by actively predicting the predicted mask quality.
* Using more achors (multiple scales per FPN level) can indeed improve the performance.

Other noteworthy points:
------
* The fast NMS to trade precision for speed.
* The deformable conv layer with intervals for the speed and performance tradeoff.
* The additional semantic segmentation loss can enhance the performance. One image pixel can have multiple labels when converting the
istance segmentation labels to semantic segmentation labels.

