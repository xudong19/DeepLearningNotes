[RetinaTrack: Online Single Stage Joint Detection and Tracking](https://arxiv.org/pdf/2003.13870.pdf) [CVPR 20]
---------------	

__TL;DR__: This paper also aims at combining the embedding learning mechanism with the object detection framework
to obtain fast object tracker. The major innovation is that it first take advantage the multiple-anchor at one feature map 
location to tackle the occlusion problem, and then separate the processing branches in the detection head for different anchors
to ensure that each anchor is able to learn the representation of different objects

__keywords__: MOT

__Resources__: [[Gitlab]] 

__Other Notable Info__: 

<br/>    

General Comments:
------
* The main innovation is to make use of the multple-anchor design to address the occlusion problem and to separate the 
processing branches for each anchor so that each anchor can learn representations independently from each other.


Key ideas and technical details:
------
* There are two ways to split the shared processing layers. One way is to split based on tasks, namely cls, reg, and embedding. 
Another way is to split based on anchors, which has been long overlooked. The combination of these two ways of splitting (and sharing) can result in many possible detection head design. This paper explore different combinations and settle at early splitting for anchors and late
sharing for tasks.

Other noteworthy points:
------
* triplet loss with [BatchHard strategy](https://arxiv.org/pdf/1703.07737.pdf) were used to train the embedding.



