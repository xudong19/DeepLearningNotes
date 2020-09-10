[FCOS: Fully Convolutional One-Stage Object Detection](https://arxiv.org/pdf/1904.01355.pdf) [ICCV 19]
---------------	

__TL;DR__: This paper aims to design a anchor-free method to streamline the object detection pipeline. The proposed method differs with anchor-based method in two essential ways, the regression target and the definition of positive and negative samples (paper [ATSS](./ATSS.md) has a better analysis on this).

__keywords__: OD

__Resources__: [[Github](https://github.com/tianzhi0549/FCOS)] 

__Other Notable Info__: [[Chuhua Shen's group](https://cs.adelaide.edu.au/~chhshen/)]

<br/>    

General Comments:
------
* This paper achieved STOA performance with the anchor-free method by several inventions, including the centerness loss, the procedure to assign regression target, and the full use of the FPN to solve the object size variation (with added scalar to accommodate the regress difference at each level). 
* The experiment is abundant and result is promissing. The anchor-free method is getting its way. 

Key ideas and technical details:
------
* The switch from the detection of the single center and then regression of the w, h, to the detection of multiple centers and hence regression of l, t, r, b, is pretty novel. (Though it is not invented by this paper)
* The centerness loss to both facilitate a better representation learning and ease the burden of NMS to solve the excessive prediction problem. 
* The way to assign the regress target based on if the pixel is located within the GT object box. 


Other noteworthy points:
------
* The abundant experiments to compare the Best Possible Recalls (BPR) with that of RetinaNet. It fundamentally eliminate the concern of the problem of recall for anchor-free method.



