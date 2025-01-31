[VoxPoser: Composable 3D Value Maps for Robotic Manipulation with Language Models](https://voxposer.github.io/voxposer.pdf) [CoRL 23]
---------------	

__TL;DR__: Use LLM and LVM to generate affordance and constraints in the 3D space, represented as voxels, and then use LLM to write code to convert into constraints. Use an open source motion planner to generate trajectory.

__keywords__: bla-bla

__Resources__: [[Github](blabla)] 

__Other Notable Info__: [blabla](blabla)

<br/>    

General Comments:
------
* The key insight is that pretrained LLM and LVM are good at 3D reasoning, but not so good at directly generating actions.

Key ideas and technical details:
------
* The role of dynamic model when contact happens, this account for some errors
* model predictive control (MPC), takes in the future predictions and the rewards at each state, to generate a trajectory that maximizes the accumulated rewards.
* My thought:  there are many stages in a planning tasks, use language to do task breakdown, reasoning, and use LVM to do spatial reasoning and generate perception outputs. The very last step is to generate actions, which in this paper is through cost map coded by LLM and a traditional solver, but in my opinion is not the best idea. We will need to train a separate action model, or a separate action decoder on top of LVM model for action decoding.
* If the action model were to be separated from the Vision(perception) model, that's the best interface between them? I do not think the code written by LLM is a good idea. 

Other noteworthy points:
------
* 
* 

Screenshots:
------
<!-- ![Image1](../img/pointnet_net.png "Architecture") -->

