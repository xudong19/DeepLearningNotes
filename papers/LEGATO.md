[LEGATO: Cross-Embodiment Imitation Using a Grasping Tool](https://arxiv.org/pdf/2411.03682) [RAL25]
---------------	

__TL;DR__: To solve the cross-embodiment problem for gripper grasping, the paper proposes to use a unified gripper handle,
Human can use the gripper directly to do demo, and the gripper can be seamless plugged into
different robots. 

__keywords__: Gripper hardware

__Resources__: [[Github](https://github.com/ut-hcrl/LEGATO)] 

__Other Notable Info__: [Project Page](https://ut-hcrl.github.io/LEGATO/)

<br/>    

General Comments:
------
* The same gripper used by human demo is used by different robots. So the manipulation of the gripper is the unified. The rest of the movement is solved by inverse kinematics (IK).
* Denavit-Hartenberg Bidirectional (DHB) invariant representation as training regularization for different embodiment.
* built-in camera in the gripper. 
*

Key ideas and technical details:
------
* DHB transformation to remove all the viewpoint related and embodiment related variants and only keep the invariant movements.
* Loss CE to predict grasping action of the gripper; loss reg and loss NLL to predict gripper movement.

Other noteworthy points:
------
* Spot robot yeild the best result, showing that whole-body motion capacity and some redundancy can improve success rate.
* 

Screenshots:
------
<!-- ![Image1](../img/pointnet_net.png "Architecture") -->

