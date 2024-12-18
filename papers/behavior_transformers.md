[Behavior Transformers: Cloning k modes with one stone](https://arxiv.org/pdf/2206.11251) [NIPS 22]
---------------	

__TL;DR__: blablablablabla

__keywords__: bla-bla

__Resources__: [[Github](blabla)] 

__Other Notable Info__: [blabla](blabla)

<br/>    

General Comments:
------
* Predict action (a) from obvervation (o)
* Use kmeans to bin the continuous actions into discretized bins
* Use transformer to predict the action bin, coupled with an offset head.

Key ideas and technical details:
------
* If there is k bins, the offset head will predict k offsets, one offset per bin.
* In training, the offset loss only applied to the GT bin
* Focol loss for cls; MSE for offset prediction.

Other noteworthy points:
------
* 
* 

Screenshots:
------
<!-- ![Image1](../img/pointnet_net.png "Architecture") -->

