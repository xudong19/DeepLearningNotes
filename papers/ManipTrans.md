[ManipTrans: Efficient Dexterous Bimanual Manipulation Transfer via Residual Learning](https://arxiv.org/pdf/2503.21860) [CVPR25]
---------------	

__TL;DR__: blablablablabla

__keywords__: bla-bla

__Resources__: [[Github](https://github.com/ManipTrans/ManipTrans)] 

__Other Notable Info__: [Project Page](https://maniptrans.github.io/)

<br/>    

General Comments:
------
* Two layers of transferring: coarse-imitation to replicate the hand pose;
fine-imitation (residual learning) to replicate the hand-object joint manipulation.
Both models are RL based models
* coarse-imitatation learning: rewards are: wrist-tracing; finger imitation; and smoothness. 
This is similar to retargetting and IK
* Residual learning to handle the fine-grained hand-object interaction, just
like a low-level controller.
* fine-imitation (residual learning): rewards: object following; reasonable contact force.
The state info: object position, speed, trajectory, mass center, gravitational force,
[BPS representation](https://arxiv.org/pdf/1908.09186), hand-object distance, and contact force; 
* The key is to have a very good simulator that can simulate interaction, which in turn requires
the MoCap data to capture hand model the hand and object data very accurately, e.g. shape,
mesh, materials, position, velocity, ect.

Key ideas and technical details:
------
* data needed to train the models:
  - accurate human hand tracking, fingure joint angles, and wrist position, and mesh modeling
  - accurate object tracking and mesh modeling
  - existing datasets that satisfies: [Oakink2](https://github.com/oakink/OakInk2),
  [FAVOR](https://kailinli.github.io/FAVOR/) which all ultimately derived from
  [MANO model](https://mano.is.tue.mpg.de/).
* Once the model is trained, it can apply to new data. The learned fine-imitation
serves as a stabalizing low-level controller, when deployed into real world, the
result is really amazing.
* target position + PD controller. The final produced robot hand pose still serves
as target position, it will needs a PD position controller to control the robot hand
eventually.
* To make it work in real-world, tactile sensing is needed (to get contact force),
and further joint-angle optimization is needed 

Other noteworthy points:
------
* smooth reward function is defined in [PHC](https://www.zhengyiluo.com/PHC-Site/) paper 
* A lot of tricks to make the residual learning work in simulator, which could be
a big limitation of the method.

My questions:
------


Screenshots:
------
<!-- ![Image1](../img/pointnet_net.png "Architecture") -->

