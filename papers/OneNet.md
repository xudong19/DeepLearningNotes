[OneNet: Towards End-to-End One-Stage Object Detection](https://arxiv.org/pdf/2012.05780.pdf) [arXiv 20]
---------------	

__TL;DR__: This paper offers a key insight to the root cause of dense detectors (detectors making dense predictions), which is that the cls cost is not considered in the label assignment process. After incorporating cls cost in label assignment, the NMS can be totally eliminated while still achieving SOTA performance.

__keywords__: OD

__Resources__: [[Github](https://github.com/PeizeSun/OneNet)] 

__Other Notable Info__: 

<br/>    

General Comments:
------
* The misalignment between label assignment and network optimization objective is the root cause for the need of dense prediction.
* The regression tends to lead to a smoothing effect, which might account for the continuous distribution from totally negative prediction to the best positive prediction. While Adding the cls cost can enable a step function alike effect to change from negative samples to positive samples. This step function allows the realization of predictions in a sparse manner.
* The gt boxes and pred boxes matching algorithm is a straightforward greedy matching. Each gt box will pick the pred box with smallest cost.

Key ideas and technical details:
------
* Adding cls cost into the label assignment process.

Other noteworthy points:
------
* The multi-head training design to facilitate training while maintaining inference speed by using single-head during inference.


