[EgoScale: Scaling Dexterous Manipulation with Diverse Egocentric Human Data](https://arxiv.org/pdf/2602.16710)
---------------	

__TL;DR__: Using ego-centric human video data in pretraining can make the foundation
model really generalize

__keywords__: 

<!-- __Resources__: [[Github](blabla)]  -->

__Other Notable Info__: [Project Page](https://research.nvidia.com/labs/gear/egoscale/)

<br/>    

General Comments:
------
* Using ego-centric human video data in pretraining can make the foundation model really generalize, and more importantly, there is scaling law in pretraining. The amount of data and compute used in pretraining directly correlates with the final downstream task scores
* Finger movement and wrist 6D post are the standard representation for data and model learning
* The pretraining is mainly to learn the real world dynamic, common sense, robustness and scene generalization
* the post-training is to improve the task performance.
* the wrist camera for dexterous hands is very important
* the data receipe: 
 - pretraining: very large amount (20K hours) pretraining data 
 - Mid-training: aligned 30 human demo data + 5 teleop robot data per task, and learn for 5 tasks
 - post training: 100 teleop robot data per task, and learn for 5 tasks

* when adapted to new skills (never seen in mid-training)
 - 1 teleop robot data + 100 human demo data

Key ideas and technical details:
------
* transfer to new embodiment (G1 with 7 DoF tri-finger hand)
 - human data pretraining + G1 data in mid-training and post training is better than without human data pretraining. But the exact the amount of data used is not disclosed in the paper.

Other noteworthy points:
------
* In finger 4, we can see that the midtraining is mostly helpful for high-precision tasks like using syringe.
* 25 keypoints per human hand representation is later retargetted into 22-DoF dexterous hand representation


Other comments:
------
* this is an natural extension to existing work like egomimic, PH2D, DexWild, but with higher magnitude of ego-centric data and more scable data collection method (basically no hardware required).
* large amount, scaling ego centric data for pre-training is the new trend in 2026 and onward.
* the pretraining data does not have wrist camera, what if we add it as well?
* the mid-training require human wear gloves and vive tracker, and mimic the robot actions, which is unnatural and demanding for human data collector. Is it really needed? Can we remove the mid-training by simply adding more high quality robot trajectory data?

Screenshots:
------
<!-- ![Image1](../img/pointnet_net.png "Architecture") -->

