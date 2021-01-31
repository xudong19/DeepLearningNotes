[Sparse R-CNN: End-to-End Object Detection with Learnable Proposals](https://arxiv.org/pdf/2011.12450.pdf) [arXiv 20]
---------------	

__TL;DR__: This paper propose a new RCNN architecture to achieve sparse predictions at every stage. The realization of sparse predictions results from the dynamic head with allows the interaction between regional feature map (roi feature) and the learnable proposal feature. 

__keywords__: OD

__Resources__: [[Github](https://github.com/PeizeSun/SparseR-CNNt)] 

__Other Notable Info__: 

<br/>    

General Comments:
------
* The paper make network to directly output a sparse set of proposals and then iteratively refine the proposals before making final predictions.
* The proposals in the very first round are almostly randomly generated, which only reflects the statistics of the whole dataset. In this sense, it is a bit like the learned object queries in [DETR](https://arxiv.org/pdf/2005.12872.pdf). 
* The refinement of proposal is done by a dynamic head, which takes in the roi feature (the feature on the feature map which the proposal locates) and an additional learnt feature vector (proposal feature). The workflow of the head is as follows: 1. apply self-attention to the additional learnt feature vector ([PyTorch Module](https://pytorch.org/docs/stable/generated/torch.nn.MultiheadAttention.html)); 2. Apply matrix multiplication between roi feature and proposal feature; 3. Obtain object feature by a linear layer and addition with old proposal feature; 4. the object feature will be used for cls and reg, and also used as the new proposal feature for the next refinement. 
* The matching between pred boxes and gt boxes (in order to calculate loss) as each stage is by hungarian assignment.
* Overall the algorithm proposed in this paper is very delicate and crafty and a bit complex for implementation.


Key ideas and technical details:
------
* Based on the general framework of RCNN, generate a sparse set of proposals at each stage instead of a dense one as by region proposal network. In order to make it work, a delicate dynamic head is designed to enable feature interactions.

Other noteworthy points:
------
* Based on its ablation study, both iterativeness and dynamicness played a big role in the performance.
* Feature resue (the proposal feature for previous stage will be concaenated into current proposal feature for next stage) also plays a big role.
* Both the self-attention and the feature interation play a big role.
* More proposals and more refinement stages can improve performance, but with a diminishing return.


