[DexVLG: Dexterous Vision-Language-Grasp Model at Scalele](https://arxiv.org/pdf/2507.02747) [ICCV25]
---------------	

__TL;DR__: from RGBD image (colored point cloud) to generate a grasp pose (6D wrist + finger joints),
conditioned on language instructions. First generate ground truth grasp in simulator using
optimization based method. Then train a network to do the same thing.

__keywords__: bla-bla

__Resources__: [[Github](blabla)] 

__Other Notable Info__: [Project Page](blabla)

<br/>    

General Comments:
------
* from RGBD image (colored point cloud) to generate a grasp pose (6D wrist + finger joints),
conditioned on language instructions
* The pose will be the "policy". It's open loop policy in some sense.
* validate the pose in simulator (isaac-gym).
* then validate in the real hardware.
* It's basically a vision problem.
* very complicated pipeline:
 - generate meshes and parts of objects
 - initialize grasp poses by doing oriented bb detection on parts
 - using optimization based method to generate the final grasp pose in simulator. 
 - this pose will be used as ground truth dataset and will train a network to do
 the same thing from a RGBD image and language instructions


Key ideas and technical details:
------
* using existing model tools to do : Objaverse object -> meshes -> parts
* 

Other noteworthy points:
------
* 
* 

Screenshots:
------
<!-- ![Image1](../img/pointnet_net.png "Architecture") -->

