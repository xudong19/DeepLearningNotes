[End-to-End Object Detection with Fully Convolutional Network](https://arxiv.org/pdf/2012.03544.pdf) [arXiv 20]
---------------	

__TL;DR__: This paper attempts to design a fully end-to-end detector (mainly to remove NMS) by three innovations: 1. the one-to-one label assignment (cls loss + reg loss + spatial prior), 2. the max filtering across FPN stages, 3. auxiliary loss with normal one-to-many label assignment.

__keywords__: OD

__Resources__: [[Github](https://github.com/Megvii-BaseDetection/DeFCN)] 

__Other Notable Info__: 

<br/>    

General Comments:
------
* Similar to [OneNet](OneNet.md), this paper also focuses on the label assignment to remove NMS. But differently, the label assignment rule proposed in this paper is a combination of cls loss, reg loss, and also spatial prior. 
* Also notably, the simple one-to-one label assignment rule alone is not enough to achieve performance on par with SOTA. Therefore, this paper propose the the max filtering across FPN stages to further supress the duplicate predictions across adjacent FPN stages, and also the auxiliary loss to provide more supervision signals.
* The max filtering is inspired and similar to the max pooling in [CenterNet](https://arxiv.org/pdf/1904.07850.pdf), which is arguably a variant of NMS. In this sense, the paper did not fully realize its ambition. 
* As far as I understand, the purpose of the max filtering across FPN stages and the purpose of auxiliary loss are a bit contradicting to each other, as one is to supress duplicate prediction and the other is to facilitate duplicate predictions. The coexistence of the two mechanisms suggests rooms to improve on the algorithm design. 

Key ideas and technical details:
------
* The key inside is also that the one-to-one label assignment is the key to end-to-end detector.
* The 3D max filtering is designed to supress duplicate predictions across FPN stages
* The auxliary loss to increase the supervision signals during the training.

<!-- Other noteworthy points:
------
*  -->


