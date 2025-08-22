[DexWrist: A Robotic Wrist for Constrained and Dynamic Manipulation](https://arxiv.org/pdf/2507.01008) [RSS25]
---------------	

__TL;DR__: A new wrist design 

__keywords__: Activities of Daily Living (ADL)

__Resources__: [[Github](blabla)] 

__Other Notable Info__: [Project Page](blabla)

<br/>    

General Comments:
------
* A wrist design, decoupled parallel kinematic mechanism, simulatable, controllable,
backdriveable, and torque transparent
* 2 DoF
* the mocap device for teleop can be anything, e.g. spacemouse etc.

Key ideas and technical details:
------
* improvement on teleoperation: faster, more feasible, shorter execution time, and higher success rate
* improvement on robot learning: tested on behaviorhigher success rate 
* This wrist performance is very close to human, according to table I in the table
* remove the last two joints of piper arm, to keep the retrofitted arm still 6 DoF
* MoCap method for TeleOp is based on [VisionProTeleop](https://github.com/Improbable-AI/VisionProTeleop)

Other noteworthy points:
------
* Behavior cloning. 141 demo data
* continuous 6D rotation representation for end effector pose as proposed in
[RotationContinuity](https://github.com/papagina/RotationContinuity)

Screenshots:
------
<!-- ![Image1](../img/pointnet_net.png "Architecture") -->

