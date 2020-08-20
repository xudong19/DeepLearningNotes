[Bridging the Gap Between Anchor-based and Anchor-free Detection via Adaptive Training Sample Selection](https://arxiv.org/pdf/2004.01888.pdf) [CVPR 20]
---------------	

__TL;DR__: This paper digged into the performance gap between anchor-free method (concretely [FCOS](https://arxiv.org/pdf/1904.01355.pdf)) and anchor-based method ([RetinaNet](https://arxiv.org/pdf/1708.02002.pdf)). The key finding is that after fixing all other control variables the same, the performance gap essentially comes from the different definitions of positive and negative samples in training. Inspired of the finding, the paper proposed a new adaptive training sample selection (ATSS) mechanism to further boost the performance.

__keywords__: OD

__Resources__: [[Github](https://github.com/XiongweiWu/ATSS)] 

__Other Notable Info__: 

<br/>    

General Comments:
------
* The paper made good distinctions among the currently burgeoning anchor-free methods. Basically the paper categorize them into two keypoint-based methods (e.g. CenterNet) and center-based methods (e.g. FCOS). While the keypoint-based methods derive from the keypoint detection and are quite different from conventionaly mainstream detectors, the center-based methods shares a lot of similarities with conventional anchor-based detectors. The key differences between anchor-based methods and the center-based methods are 1. # of anchors tiled per location; 2. the definition of positive and negative samples; 3. the regression status.
* The paper further argues that among the three differences, only the definition of positive and negative samples has a significant influence on the performance. 
* The new ATSS mechanism characterizes a few principles: 1. Selecting candidates based on the center distance be- tween anchor box and object; 2. Using the sum of mean and standard deviation as the IoU threshold; 3. Limiting the positive samples’ center to object; 4. Maintaining fairness between different objects. 
* Extensive experiments shows that equiped with the ATSS, the gap between anchor-based method and center-based method is almost filled, and what's more, the number of anchors and the anchor shapes at each locations do not make any difference to the performance. 

<!-- Key ideas and technical details:
------
*  -->

Other noteworthy points:
------
* Table 1 of the papers shows some effective general tricks to increase performance, including GroupNorm, GIoU loss, In GT Box (meaning limiting positive samples inside gt object box), CenterNess, and scalar (adding trainable scalar to each feature pyramid). 



