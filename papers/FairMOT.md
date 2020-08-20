[A Simple Baseline for Multi-Object Tracking](https://arxiv.org/pdf/2004.01888.pdf) [ECCV 20?]
---------------	

__TL;DR__: The paper investigated the inferior performance of MOT algorithms when the detection and ReID are combined in
one stage. The proposed reason for the inferior performance is the mismatch between the anchor position on which the embedding feature is regressed on and the true object position to which the embedding feature corresponds to. The proposed solution is to use anchor-free detection architecture with higher feature map resolution .

__keywords__: MOT

__Resources__: [[Github](https://github.com/ifzhang/FairMOT)] 

__Other Notable Info__: 

<br/>    

General Comments:
------
* The key insight of this paper is the revelation that the mismatch between the achnor location and the object location which the ReID feature should correspond to is the root casue for the performance degradation of the one-step architecture. The proposed solution is thus to use anchor-free detection framework
* The other two mechanisms used in the paper to boost the performance is the multy-layer feature aggregation (e.g. [HRNet](https://arxiv.org/pdf/1904.04514.pdf), [DLR](https://arxiv.org/pdf/1707.06484.pdf)), and the optimal dimensinality of the ReID features (the paper claims that over-parameterized ReID features actually harms the performance due to unlimited training data and hence overfitting)
* Though very simple, the model achieves SOTA result in multiple datasets, including 2DMOT15, MOT16, MOT17, MOT20 ([link](https://paperswithcode.com/paper/a-simple-baseline-for-multi-object-tracking))

<!-- Key ideas and technical details:
------
*  -->

Other noteworthy points:
------
* The resolution of the feature map that the detection and ReID head can operate on really matters for the performance. Changing the resultion from 1/8 to 1/4 greatly increase the peroformance becasue of the mitigation of the misalignment between the anchor and the object. But changing the resultion from 1/4 to 1/2 did not increase the performance, for the 1/2 feature did not catch high enough semantics and is prone to appearance variations. 



