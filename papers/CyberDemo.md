[CyberDemo: Augmenting Simulated Human Demonstration for Real-World Dexterous Manipulation](https://arxiv.org/pdf/2402.14795) [CVPR 2024]
---------------	

__TL;DR__: Human demo (using teleoperation) to collect data in the simulation. Use data augmentation to for domain adaption and curriculum learning to train a robust policy with imitation learning. The policy can transfer to real very well and is also robust to different setup perturbations.

__keywords__: DH, IL, S2R

<!-- __Resources__: [[Github](blabla)]  -->

<!-- __Other Notable Info__: [blabla](blabla) -->

<br/>    

General Comments:
------
* Take full advantage of the data augmentation in the simulation, due to the access of the oracle information. 
* random camera view
* random light and texture
* Diverse objects (perturbation to the object shape). To adapt demo trajectory, add noise to the demo trajectory as well and generate new successful demo trajectories in a sample-intensive way.
* ramdom object pose. to adapt demo trajectory, first compute the sensitivity of each action in the demo trajectory, ande then distribute the total amount of end pose change into all the actions based on the sensitivity.
* curriculum learning: gradually increasing the degree of augmentation to learn a robust policy

Key ideas and technical details:
------
* 
* 

Other noteworthy points:
------
* Domain Randomization (DR) vs Domain Adaption (DA)
* Domain adaptation (DA) refers to a set of transfer learning strategies developed to align the data distribution between sim and
real.
* domain randomization [50, 71] generates simulated environments with randomized properties and trains a model function across all of them.
* RL is very sample intensive and DR is also very sample intensive, and thus it's only feasible in the simulation.


Screenshots:
------
<!-- ![Image1](../img/pointnet_net.png "Architecture") -->

