[Grasp as You Say: Language-guided Dexterous Grasp Generation](https://arxiv.org/pdf/2405.19291) [NeurIPS 2024]
---------------	

__TL;DR__: blablablablabla

<!-- __keywords__: bla-bla -->

<!-- __Resources__: [[Github](blabla)]  -->

__Other Notable Info__: [Project Page](https://isee-laboratory.github.io/DexGYS/)

<br/>    

General Comments:
------
* Use the open-source human grasping dataset [OakInk](https://github.com/oakink/OakInk)
to retarget human hand data to robot hand data. The retargeting is optmization
based, with figure-tip position objective, and preserving the contact area of
the optimized pose consistent with the output objectives.
* Once the robot-object grasp dataset is obtained, the goal is to generate robot
hand motion from language commands. The generation has two steps:
  - generation model with the goal of following command and diversity motion
  - regression model to fine tune the poses
* The ground-truth language guidance in the training dataset is obtained through
"LLM-assisted Language Guidance Annotation".

Key ideas and technical details:
------
* 
* 

Other noteworthy points:
------
* 
* 

Screenshots:
------
<!-- ![Image1](../img/pointnet_net.png "Architecture") -->

