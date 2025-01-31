[ReKep: Spatio-Temporal Reasoning of Relational Keypoint Constraints for Robotic Manipulation](https://arxiv.org/pdf/2409.01652) [CoRL24]
---------------	

__TL;DR__: blablablablabla

__keywords__: bla-bla

__Resources__: [[Github](https://github.com/huangwl18/ReKep)] 

__Other Notable Info__: [Project Website](https://rekep-robot.github.io/)

<br/>    

General Comments:
------
* learning the constraints between robots and enviroments. 
* Use off-the-shelve vision and large models to generate constraints, and use a traditional solvers to solve a robot trajectory
* Use DINOv2 + SAM to generate keypoints and then use GPT4o to write code for constraints
* overall, this is a great assembly of vision foundation models and a good attempt to use model to write code. The real "planning" part is done by using a public solver.

Key ideas and technical details:
------
* DINOv2 is better than CLIP and ViT
* The prompt to GPT4o is crazily long and detailed
* The kepoints tracking is not trivial 
* evan with a set of contraints writen by GPT4o, there are still some more regularizations and other costs/objectives to be considered.
* sampling-based global optimization Dual Annealing [129] in the first iteration to quickly search the full space, which is followed by a gradient-based local optimizer SLSQP [130]

Other noteworthy points:
------
* 
* 

Screenshots:
------
<!-- ![Image1](../img/pointnet_net.png "Architecture") -->

