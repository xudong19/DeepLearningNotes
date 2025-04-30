[DEXTERITYGEN: Foundation Controller for Unprecedented Dexterity](https://arxiv.org/pdf/2502.04307) [RSS 25]
---------------	

__TL;DR__: blablablablabla

<!-- __keywords__: bla-bla -->

<!-- __Resources__: [[Github](blabla)]  -->

__Other Notable Info__: [Project Page](https://zhaohengyin.github.io/dexteritygen/)

<br/>    

General Comments:
------
* train a diffusion policy model that takes in proprioception state info, mode conditioning and generate the actions.
* difussion policy to learn an action model, to generate next pose from state.
* use distance between teleop pose and the generated pose as tunning factor in the denoising
process. It's gradient guided in the denosing process.
* When training the model, there is no input cmd and no motion preserving. In training,
the goal is to train a good diffusion model to generate actions. In inference,
the motion preserving is added as a modification to the denosing process. This
fully leverages the denoising process.

Key ideas and technical details:
------
* Use RRT to generate anygrasp dataset. The grasp data is set as the reward/goal
to grasp process. The goal is sampled from nearest grasp pose from current pose.
* Train in simulation, with wrist pose and other domain randomization technique
to increase the robustness. Zero-shot sim-2-real transfer.
* U-net diffusion model architecture

Other noteworthy points:
------
* no vision inputs. Just proprioception state info from motor feedback. Use vision
inputs will make it more chanleging for sim-2-real transfer.
* Diffusion model generate 3D (x,y,z) keypoints as the next state, then a MLP based
inverse dynamics model to learn the mapping into actions (joint angles)
* Very nice summary of the chanllenges for human teleoperation and sim-to-real RL
  - human telop: partial observation; embodiment gap; motion complexity; lack of force input
  - Sim2Real RL: vison-based control need costly visual domain randomization; reward engineering
  is hard for long-horizon contact-rich tasks.

My thoughts:
------
* It's kinda amazing that no touch, no vision is needed, but the model can still
automatically stablize the control.
* Can we try to use motion conditioning during training as well? Will it improve stuff?
* what happens for no grasping poses


Screenshots:
------
<!-- ![Image1](../img/pointnet_net.png "Architecture") -->

