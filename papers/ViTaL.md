[Touch begins where vision ends: Generalizable policies for contact-rich manipulation](https://arxiv.org/pdf/2506.13762) [RSS25]
---------------	

__TL;DR__: blablablablabla

__keywords__: bla-bla

__Resources__: [[Github](blabla)] 

__Other Notable Info__: [Project Page](blabla)

<br/>    

General Comments:
------
* Imitation learning (VLA) is good for tabletop, but struggle with high-precision and contact-rick
tasks
* RL good for this but cannot generalize. It overfit to specific task and specific scene.
* tactile: robust to lighting, clustter, occlusion. direct localized feedback about force and slip.
But has no spatial awareness and coarse alignment
* RL for residual learning (Residual RL), providing offset (refinement) to VLA model
* foundation model for data augmentation, visual background augmentation.
* using VLM to decouple tasks dynamics from environment configuration
* Offline (regularly trained VLA) + online RL refinement.


Key ideas and technical details:
------
* for visual robustness: background augmentation: DIFT, SAM, and XMem 
* ResNet for vision encoding, and MLP for tactile encoding, and then pass through
transformer for action prediction.
* residual policy: 
  - actor: input: visual, tactile, and base action, output residual action
  - critic: input: visual, tactile, base action, and residual action. 
  UTD for Q-learning
  - DDPG as optimizer
  - Reward: success bit and L1 distance from goal


Other noteworthy points:
------
* 
* 

Screenshots:
------
<!-- ![Image1](../img/pointnet_net.png "Architecture") -->

